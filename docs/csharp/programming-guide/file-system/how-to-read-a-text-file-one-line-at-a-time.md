---
title: Como ler um arquivo de texto uma linha de cada vez (Visual C#)
ms.date: 07/20/2015
helpviewer_keywords:
- ReadLine method [C#]
- reading text files, line by line
- text files [C#]
ms.assetid: d62e22c5-a13c-48db-af9b-f10c801b0cb1
ms.openlocfilehash: b31e3f0164b2a2094e84263702c52c2817219d20
ms.sourcegitcommit: a1e35d4e94edab384a63406c0a5438306873031b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/21/2018
ms.locfileid: "42751972"
---
# <a name="how-to-read-a-text-file-one-line-at-a-time-visual-c"></a>Como ler um arquivo de texto uma linha de cada vez (Visual C#)
Este exemplo lê o conteúdo de um arquivo de texto, uma linha por vez, em uma cadeia de caracteres usando o método `ReadLine` da classe `StreamReader`. Cada linha de texto é armazenada na cadeia de caracteres `line` e exibida na tela.  
  
## <a name="example"></a>Exemplo  
  
```csharp
int counter = 0;  
string line;  
  
// Read the file and display it line by line.  
System.IO.StreamReader file =   
    new System.IO.StreamReader(@"c:\test.txt");  
while((line = file.ReadLine()) != null)  
{  
    System.Console.WriteLine(line);  
    counter++;  
}  
  
file.Close();  
System.Console.WriteLine("There were {0} lines.", counter);  
// Suspend the screen.  
System.Console.ReadLine();  
```  
  
## <a name="compiling-the-code"></a>Compilando o código  
 Copie o código e cole-o no método `Main` de um aplicativo de console.  
  
 Substitua `"c:\test.txt"` pelo nome do arquivo real.  
  
## <a name="robust-programming"></a>Programação robusta  
 As seguintes condições podem causar uma exceção:  
  
-   O arquivo pode não existir.  
  
## <a name="net-framework-security"></a>Segurança do .NET Framework  
 Não tome decisões sobre o conteúdo do arquivo com base no nome do arquivo. Por exemplo, o arquivo `myFile.cs` pode não ser um arquivo de origem do C#.  
  
## <a name="see-also"></a>Consulte também  
 <xref:System.IO?displayProperty=nameWithType>  
 [Guia de Programação em C#](../../../csharp/programming-guide/index.md)  
 [Sistema de arquivos e o Registro (Guia de Programação em C#)](../../../csharp/programming-guide/file-system/index.md)
