---
title: Error 语句
ms.date: 07/20/2015
f1_keywords:
- vb.error
helpviewer_keywords:
- Error statement [Visual Basic], syntax
- Error statement [Visual Basic]
- Error keyword [Visual Basic]
- run-time errors [Visual Basic], codes
- errors [Visual Basic], simulating
ms.assetid: 85cd5c59-5224-4f02-aaf5-fcfefab17a29
ms.openlocfilehash: 668ffbc7b8db73a706c5771bb0734a77f8fc0206
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351235"
---
# <a name="error-statement"></a>Error 语句
模拟出现错误的情况。  
  
## <a name="syntax"></a>语法  
  
```vb  
Error errornumber  
```  
  
## <a name="parts"></a>部件  
 `errornumber`  
 必需。 可以是任何有效的错误号。  
  
## <a name="remarks"></a>备注  
 支持 `Error` 语句，以便向后兼容。 在新代码中，特别是在创建对象时，使用 `Err` 对象的 `Raise` 方法来生成运行时错误。  
  
 如果定义了 `errornumber`，则 `Error` 语句将在为该对象的 `Err` 属性分配以下默认值之后调用错误处理程序：  
  
|属性|值|  
|--------------|-----------|  
|`Number`|指定为 `Error` 语句的参数的值。 可以是任何有效的错误号。|  
|`Source`|当前 Visual Basic 项目的名称。|  
|`Description`|对应于指定的 `Number`的 `Error` 函数的返回值的字符串表达式（如果此字符串存在）。 如果字符串不存在，`Description` 包含一个长度为零的字符串（""）。|  
|`HelpFile`|适当的 Visual Basic 帮助文件的完全限定驱动器、路径和文件名。|  
|`HelpContext`|对应于 `Number` 属性的错误的相应 Visual Basic 帮助文件上下文 ID。|  
|`LastDLLError`|无.|  
  
 如果没有错误处理程序，或者未启用任何错误处理程序，则将创建一个错误消息并将其显示在 `Err` 对象属性中。  
  
> [!NOTE]
> 某些 Visual Basic 主机应用程序无法创建对象。 请参阅宿主应用程序的文档，以确定它是否可以创建类和对象。  
  
## <a name="example"></a>示例  
 此示例使用 `Error` 语句生成错误号11。  
  
```vb  
On Error Resume Next   ' Defer error handling.  
Error 11   ' Simulate the "Division by zero" error.  
```  
  
## <a name="requirements"></a>要求  
 **命名空间：** [Microsoft](../../../visual-basic/language-reference/runtime-library-members.md)  
  
 **程序集：** Visual Basic 运行时库（在 Microsoft. .dll 中）  
  
## <a name="see-also"></a>另请参阅

- <xref:Microsoft.VisualBasic.ErrObject.Clear%2A>
- <xref:Microsoft.VisualBasic.Information.Err%2A>
- <xref:Microsoft.VisualBasic.ErrObject.Raise%2A>
- [On Error 语句](../../../visual-basic/language-reference/statements/on-error-statement.md)
- [Resume 语句](../../../visual-basic/language-reference/statements/resume-statement.md)
- [错误消息](../../../visual-basic/language-reference/error-messages/index.md)
