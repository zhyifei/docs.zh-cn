---
title: Mid 语句 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.MidB
- vb.Mid
helpviewer_keywords:
- substrings [Visual Basic], Mid statement
- strings [Visual Basic], substrings
- Mid statement [Visual Basic]
- strings [Visual Basic], replacing
ms.assetid: 2b82d7a8-9646-4cb0-bec5-80abc98297bf
ms.openlocfilehash: a653e63ded04616b6b0c6bdfb26a0a673d9299fc
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "44061645"
---
# <a name="mid-statement"></a>Mid 语句
替换指定的数目的中的字符`String`变量与另一字符串中的字符。  
  
## <a name="syntax"></a>语法  
  
```  
Mid( _  
   ByRef Target As String, _  
   ByVal Start As Integer, _  
   Optional ByVal Length As Integer _  
) = StringExpression  
```  
  
## <a name="parts"></a>部件  
 `Target`  
 必须的。 名称`String`变量来修改。  
  
 `Start`  
 必须的。 `Integer` 表达式。 字符位置`Target`文本替换的开始位置。 `Start` 使用从 1 开始的索引。  
  
 `Length`  
 可选。 `Integer` 表达式。 要替换的字符数。 如果省略，所有的`String`使用。  
  
 `StringExpression`  
 必须的。 `String` 替换的一部分的表达式`Target`。  
  
## <a name="exceptions"></a>异常  
  
|异常类型|条件|  
|--------------------|---------------|  
|<xref:System.ArgumentException>|`Start` < = 0 或`Length`< 0。|  
  
## <a name="remarks"></a>备注  
 替换的字符数是始终小于或等于中的字符数`Target`。  
  
 Visual Basic 具有<xref:Microsoft.VisualBasic.Strings.Mid%2A>函数和一个`Mid`语句。 都按指定数目的字符在字符串中，运行这些元素，但`Mid`函数将返回字符，而`Mid`语句替换的字符。 有关详细信息，请参阅<xref:Microsoft.VisualBasic.Strings.Mid%2A>。  
  
> [!NOTE]
>  `MidB`的早期版本的 Visual Basic 语句将替换中字节，而不是字符的子字符串。 它主要用于在双字节字符集 (DBCS) 应用程序中转换字符串。 所有 Visual Basic 字符串都是 Unicode，和`MidB`不再受支持。  
  
## <a name="example"></a>示例  
 此示例使用`Mid`语句，以指定的数量的字符串变量中的字符替换为另一字符串中的字符。  
  
 [!code-vb[VbVbalrStrings#5](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/mid-statement_1.vb)]  
  
## <a name="requirements"></a>要求  
 **Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)  
  
 **模块：** `Strings`  
  
 **程序集：** [!INCLUDE[vbprvbruntime](~/includes/vbprvbruntime-md.md)]  
  
## <a name="see-also"></a>请参阅  
 <xref:Microsoft.VisualBasic.Strings.Mid%2A>  
 [字符串](../../../visual-basic/programming-guide/language-features/strings/index.md)  
 [Visual Basic 中的字符串简介](../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
