---
title: "如何：确定对象变量引用的类型 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- TypeOf operator [Visual Basic], determining object variable type
- variables [Visual Basic], object
- object variables [Visual Basic], determining type
ms.assetid: 6f6a138d-58a4-40d1-9f4e-0a3c598eaf81
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5dd6785ecd48be3f0455de63b9e3f13a485ddbb2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-determine-what-type-an-object-variable-refers-to-visual-basic"></a>如何：确定对象变量引用的类型 (Visual Basic)
对象变量包含指向存储在其他位置的数据的指针。 在运行时可以更改该数据的类型。 在任何时刻，你可以使用<xref:System.Type.GetTypeCode%2A>方法来确定当前的运行时类型，或[TypeOf 运算符](../../../../visual-basic/language-reference/operators/typeof-operator.md)若要查明当前运行时类型是否与指定的类型兼容。  
  
### <a name="to-determine-the-exact-type-an-object-variable-currently-refers-to"></a>若要确定确切类型的对象变量当前引用  
  
1.  对象变量上调用<xref:System.Object.GetType%2A>方法来检索<xref:System.Type?displayProperty=nameWithType>对象。  
  
    ```  
    Dim myObject As Object  
    myObject.GetType()  
    ```  
  
2.  上<xref:System.Type?displayProperty=nameWithType>类中，调用共享的方法<xref:System.Type.GetTypeCode%2A>检索<xref:System.TypeCode>对象的类型的枚举值。  
  
    ```  
    Dim myObject As Object  
    Dim datTyp As Integer = Type.GetTypeCode(myObject.GetType())  
    MsgBox("myObject currently has type code " & CStr(datTyp))  
    ```  
  
     你可以测试<xref:System.TypeCode>针对任何枚举成员感兴趣，例如的枚举值`Double`。  
  
### <a name="to-determine-whether-an-object-variables-type-is-compatible-with-a-specified-type"></a>若要确定是否一个对象变量的类型与指定的类型兼容  
  
-   使用`TypeOf`结合运算符[Is 运算符](../../../../visual-basic/language-reference/operators/is-operator.md)与对象进行测试`TypeOf`...`Is`表达式。  
  
    ```  
    If TypeOf objA Is System.Windows.Forms.Control Then  
        MsgBox("objA is compatible with the Control class")  
    End If  
    ```  
  
     `TypeOf`...`Is`表达式返回`True`对象的运行时类型是否与指定的类型兼容。  
  
     兼容性的条件取决于指定的类型是类、 结构或接口。 一般情况下，则类型是兼容的如果将对象与同一类型、 继承自，或实现指定的类型。 有关详细信息，请参阅[TypeOf 运算符](../../../../visual-basic/language-reference/operators/typeof-operator.md)。  
  
## <a name="compiling-the-code"></a>编译代码  
 请注意指定的类型不能为变量或表达式。 它必须已定义的类型，如类、 结构或接口的名称。 这包括内部类型，如`Integer`和`String`。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Object.GetType%2A>  
 <xref:System.Type?displayProperty=nameWithType>  
 <xref:System.Type.GetTypeCode%2A>  
 <xref:System.TypeCode>  
 [对象变量](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)  
 [对象变量值](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)  
 [Object 数据类型](../../../../visual-basic/language-reference/data-types/object-data-type.md)
