---
title: Como quebrar e combinar instruções no código (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb._
helpviewer_keywords:
- colons (:)
- line continuation
- _ line-continuation character
- ': line separator character'
- Visual Basic code, line breaks in
- Visual Basic code, line breaks
- Visual Basic code, line continuation
- long lines of code
- line terminator
- line-continuation sequence
- underscores [Visual Basic], in code
- statements [Visual Basic], line continuation in
- line breaks [Visual Basic], in code
- line-continuation character [Visual Basic]
- Visual Basic code, line continuation in
- statements [Visual Basic], line breaks in
ms.assetid: dea01dad-a8ac-484a-bb3a-8c45a1b1eccc
ms.openlocfilehash: 6bca3d62cb3e886ee08b9169d63d4c3a38247f3f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33651012"
---
# <a name="how-to-break-and-combine-statements-in-code-visual-basic"></a>Como quebrar e combinar instruções no código (Visual Basic)
Ao escrever seu código, às vezes você pode criar instruções longas que necessitam de rolagem horizontal no Editor de códigos. Embora isso não afeta a maneira como o código é executado, ele torna difícil para você ou outra pessoa para ler o código como ele aparece no monitor. Nesses casos, você deve considerar a única instrução longo de quebra em várias linhas.  
  
### <a name="to-break-a-single-statement-into-multiple-lines"></a>Para dividir uma única instrução em várias linhas  
  
-   Use o caractere de continuação de linha, que é um caractere de sublinhado (`_`), o ponto no qual você deseja que a linha de quebra. O sublinhado deve ser imediatamente precedido por um espaço e seguido imediatamente por um terminador de linha (retorno de carro).  
  
    > [!NOTE]
    >  Em alguns casos, se você omitir o caractere de continuação de linha, o compilador do Visual Basic continuará implicitamente a instrução na próxima linha de código. Para obter uma lista de elementos de sintaxe para a qual você pode omitir o caractere de continuação de linha, consulte "Continuação de linha implícita" [instruções](../../../visual-basic/programming-guide/language-features/statements.md).  
  
     No exemplo a seguir, a instrução é dividida em quatro linhas com caracteres de continuação de linha, encerrando todas, mas a última linha.  
  
     [!code-vb[VbVbcnConventions#20](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/how-to-break-and-combine-statements-in-code_1.vb)]  
  
     Usar esta sequência torna o código mais fácil de ler, online e quando impresso.  
  
     O caractere de continuação de linha deve ser o último caractere em uma linha. Você não pode segui-lo com qualquer outra coisa na mesma linha.  
  
     Existem algumas limitações sobre onde você pode usar o caractere de continuação de linha; Por exemplo, você não pode usá-lo no meio de um nome de argumento. Você pode dividir a lista de argumentos com o caractere de continuação de linha, mas os nomes individuais dos argumentos devem permanecer intactos.  
  
     Você não pode continuar um comentário usando um caractere de continuação de linha. O compilador não examina os caracteres em um comentário para um significado especial. Para um comentário de várias linhas, repita o símbolo de comentário (`'`) em cada linha.  
  
 Embora a colocação de cada instrução em uma linha separada é o método recomendado, o Visual Basic também permite que você coloque várias instruções na mesma linha.  
  
### <a name="to-place-multiple-statements-on-the-same-line"></a>Para colocar várias instruções na mesma linha  
  
-   Separe as instruções com dois-pontos (`:`), conforme mostrado no exemplo a seguir.  
  
     [!code-vb[VbVbcnConventions#10](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/how-to-break-and-combine-statements-in-code_2.vb)]  
  
## <a name="see-also"></a>Consulte também  
 [Estrutura do Programa e Convenções de Código](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)  
 [Instruções](../../../visual-basic/programming-guide/language-features/statements.md)
