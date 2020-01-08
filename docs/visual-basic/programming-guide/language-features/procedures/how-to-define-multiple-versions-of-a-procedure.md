---
title: 如何：定义一个过程的多个版本
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedures [Visual Basic], overloading
- procedures [Visual Basic], multiple versions
- procedure overloading [Visual Basic], multiple versions
ms.assetid: 71ccdd66-1b00-4b66-bee4-6926c0d696f4
ms.openlocfilehash: e8ed9a6356b7177b2c029a9280d0790a93676653
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/25/2019
ms.locfileid: "75347596"
---
# <a name="how-to-define-multiple-versions-of-a-procedure-visual-basic"></a>如何：定义一个过程的多个版本 (Visual Basic)
您*可以通过使用*相同的名称，但对于每个版本使用不同的参数列表，在多个版本中定义过程。 重载的目的是定义过程中的多个紧密相关的版本，而不必按名称对其进行区分。  
  
 有关更多信息，请参见 [Procedure Overloading](./procedure-overloading.md)。  
  
### <a name="to-define-multiple-versions-of-a-procedure"></a>定义一个过程的多个版本  
  
1. 为要定义的过程的每个版本写入 `Sub` 或 `Function` 声明语句。 在每个声明中使用相同的过程名称。  
  
2. 在每个声明中的 `Sub` 或 `Function` 关键字之前加上[Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md)关键字。 您可以选择忽略声明中的 `Overloads`，但如果将其包含在任何声明中，则必须在每个声明中包含它。  
  
3. 遵循每个声明语句，编写过程代码来处理调用代码提供与该版本的参数列表相匹配的参数的特定情况。 无需测试调用代码提供了哪些参数。 Visual Basic 将控制传递给过程的匹配版本。  
  
4. 根据需要，用 `End Sub` 或 `End Function` 语句终止过程的每个版本。  
  
## <a name="example"></a>示例  
 下面的示例定义了一个 `Sub` 过程，用于针对客户余额发布事务。 它使用 `Overloads` 关键字定义过程的两个版本，一个是按姓名，另一个按帐号接受客户。  
  
 [!code-vb[VbVbcnProcedures#72](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#72)]  
  
 调用代码可以获取客户标识作为 `String` 或 `Integer`，然后在任一情况下使用相同的调用语句。  
  
 有关如何调用 `post` 过程的这些版本的信息，请参阅[如何：调用重载过程](./how-to-call-an-overloaded-procedure.md)。  
  
## <a name="compile-the-code"></a>编译代码  
 请确保每个重载版本都具有相同的过程名称，但参数列表不同。  
  
## <a name="see-also"></a>另请参阅

- [过程](./index.md)
- [过程参数和自变量](./procedure-parameters-and-arguments.md)
- [过程疑难解答](./troubleshooting-procedures.md)
- [如何：重载带有可选参数的过程](./how-to-overload-a-procedure-that-takes-optional-parameters.md)
- [如何：重载参数数量不确定的过程](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)
- [重载过程注意事项](./considerations-in-overloading-procedures.md)
- [重载决策](./overload-resolution.md)
