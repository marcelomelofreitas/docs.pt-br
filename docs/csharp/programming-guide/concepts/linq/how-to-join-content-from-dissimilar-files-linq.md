---
title: "Como: unir conte&#250;do a partir de arquivos diferentes (LINQ) (c#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
ms.assetid: aa2d12a6-70a9-492f-a6db-b2b850d46811
caps.latest.revision: 3
caps.handback.revision: 3
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Como: unir conte&#250;do a partir de arquivos diferentes (LINQ) (c#)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Este exemplo mostra como associar dados de dois arquivos delimitados por vírgulas que compartilham um valor comum que é usado como uma chave correspondente. Essa técnica pode ser útil se você precisa combinar dados de duas planilhas ou de uma planilha em um arquivo com outro formato, em um novo arquivo. Você pode modificar o exemplo para trabalhar com qualquer tipo de texto estruturado.  
  
### Para criar os arquivos de dados  
  
1.  Copie as seguintes linhas em um arquivo chamado scores.csv e salvá\-lo em sua pasta de projeto. O arquivo representa dados da planilha. A coluna 1 é a ID do aluno, e as colunas 2 a 5 são resultados de teste.  
  
    ```  
    111, 97, 92, 81, 60  
    112, 75, 84, 91, 39  
    113, 88, 94, 65, 91  
    114, 97, 89, 85, 82  
    115, 35, 72, 91, 70  
    116, 99, 86, 90, 94  
    117, 93, 92, 80, 87  
    118, 92, 90, 83, 78  
    119, 68, 79, 88, 92  
    120, 99, 82, 81, 79  
    121, 96, 85, 91, 60  
    122, 94, 92, 91, 91  
    ```  
  
2.  Copie as seguintes linhas em um arquivo chamado names.csv e salvá\-lo em sua pasta de projeto. O arquivo representa uma planilha que contém a ID do aluno, nome e sobrenome do aluno  
  
    ```  
    Omelchenko,Svetlana,111  
    O'Donnell,Claire,112  
    Mortensen,Sven,113  
    Garcia,Cesar,114  
    Garcia,Debra,115  
    Fakhouri,Fadi,116  
    Feng,Hanying,117  
    Garcia,Hugo,118  
    Tucker,Lance,119  
    Adams,Terry,120  
    Zabokritski,Eugene,121  
    Tucker,Michael,122  
    ```  
  
## Exemplo  
  
```c#  
class JoinStrings  
{  
    static void Main()  
    {  
        // Join content from dissimilar files that contain  
        // related information. File names.csv contains the student  
        // name plus an ID number. File scores.csv contains the ID   
        // and a set of four test scores. The following query joins  
        // the scores to the student names by using ID as a  
        // matching key.  
  
        string[] names = System.IO.File.ReadAllLines(@"../../../names.csv");  
        string[] scores = System.IO.File.ReadAllLines(@"../../../scores.csv");  
  
        // Name:    Last[0],       First[1],  ID[2]  
        //          Omelchenko,    Svetlana,  11  
        // Score:   StudentID[0],  Exam1[1]   Exam2[2],  Exam3[3],  Exam4[4]  
        //          111,           97,        92,        81,        60  
  
        // This query joins two dissimilar spreadsheets based on common ID value.  
        // Multiple from clauses are used instead of a join clause  
        // in order to store results of id.Split.  
        IEnumerable<string> scoreQuery1 =  
            from name in names  
            let nameFields = name.Split(',')  
            from id in scores  
            let scoreFields = id.Split(',')  
            where nameFields[2] == scoreFields[0]  
            select nameFields[0] + "," + scoreFields[1] + "," + scoreFields[2]   
                   + "," + scoreFields[3] + "," + scoreFields[4];  
  
        // Pass a query variable to a method and execute it  
        // in the method. The query itself is unchanged.  
        OutputQueryResults(scoreQuery1, "Merge two spreadsheets:");  
  
        // Keep console window open in debug mode.  
        Console.WriteLine("Press any key to exit");  
        Console.ReadKey();  
    }  
  
    static void OutputQueryResults(IEnumerable<string> query, string message)  
    {  
        Console.WriteLine(System.Environment.NewLine + message);  
        foreach (string item in query)  
        {  
            Console.WriteLine(item);  
        }  
        Console.WriteLine("{0} total names in list", query.Count());  
    }  
}  
/* Output:  
Merge two spreadsheets:  
Adams, 99, 82, 81, 79  
Fakhouri, 99, 86, 90, 94  
Feng, 93, 92, 80, 87  
Garcia, 97, 89, 85, 82  
Garcia, 35, 72, 91, 70  
Garcia, 92, 90, 83, 78  
Mortensen, 88, 94, 65, 91  
O'Donnell, 75, 84, 91, 39  
Omelchenko, 97, 92, 81, 60  
Tucker, 68, 79, 88, 92  
Tucker, 94, 92, 91, 91  
Zabokritski, 96, 85, 91, 60  
12 total names in list  
 */  
```  
  
## Compilando o código  
 Criar um projeto que tem como alvo o .NET Framework versão 3.5 ou posterior, com uma referência a System.Core.dll e `using` diretivas para os namespaces System. LINQ e System.IO.  
  
## Consulte também  
 [LINQ e cadeias de caracteres \(c\#\)](../../../../csharp/programming-guide/concepts/linq/linq-and-strings.md)   
 [LINQ e diretórios de arquivo \(c\#\)](../../../../csharp/programming-guide/concepts/linq/linq-and-file-directories.md)