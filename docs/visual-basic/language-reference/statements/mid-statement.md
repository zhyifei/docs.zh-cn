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
ms.openlocfilehash: 212ce1f06a01c39acbce43d8d069dae3526b1b4d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963553"
---
# <a name="mid-statement"></a>Mid 语句
将`String`变量中指定数量的字符替换为另一个字符串中的字符。  
  
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
 必需。 要修改的`String`变量的名称。  
  
 `Start`  
 必需。 `Integer`表达式. 中`Target`开始替换文本的字符位置。 `Start`使用从1开始的索引。  
  
 `Length`  
 可选。 `Integer`表达式. 要替换的字符数。 如果省略, `String`则使用所有。  
  
 `StringExpression`  
 必需。 `String`替换部分的`Target`表达式。  
  
## <a name="exceptions"></a>Exceptions  
  
|异常类型|条件|  
|--------------------|---------------|  
|<xref:System.ArgumentException>|`Start`< = 0 或`Length` < 0。|  
  
## <a name="remarks"></a>备注  
 替换的字符数始终小于或等于中`Target`的字符数。  
  
 Visual Basic 具有<xref:Microsoft.VisualBasic.Strings.Mid%2A>函数`Mid`和语句。 这些元素对字符串中的指定数量的字符进行操作, 但`Mid` `Mid`当语句替换这些字符时, 函数将返回字符。 有关详细信息，请参阅 <xref:Microsoft.VisualBasic.Strings.Mid%2A> 。  
  
> [!NOTE]
> 的`MidB`早期 Visual Basic 版本语句将以字节而不是字符来替换子字符串 (而不是字符)。 它主要用于在双字节字符集 (DBCS) 应用程序中转换字符串。 所有 Visual Basic 字符串均采用 Unicode 格式, `MidB`不再受支持。  
  
## <a name="example"></a>示例  
 此示例使用`Mid`语句将字符串变量中指定数量的字符替换为另一个字符串中的字符。  
  
 [!code-vb[VbVbalrStrings#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#5)]  
  
## <a name="requirements"></a>要求  
 **命名空间：** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)  
  
 **模块:** `Strings`  
  
 **件**Visual Basic 运行库（在 Microsoft.VisualBasic.dll 中）  
  
## <a name="see-also"></a>请参阅

- <xref:Microsoft.VisualBasic.Strings.Mid%2A>
- [字符串](../../../visual-basic/programming-guide/language-features/strings/index.md)
- [Visual Basic 中的字符串简介](../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
