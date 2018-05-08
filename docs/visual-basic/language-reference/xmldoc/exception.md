---
title: '&lt;异常&gt;(Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- <exception> XML tag
- exception XML tag
ms.assetid: c0517549-171e-4dae-ab88-a9c1700b6eee
ms.openlocfilehash: f29b8e01239f46b0d56319ba3da1a8fe179a17e8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="ltexceptiongt-visual-basic"></a>&lt;异常&gt;(Visual Basic)
指定可以引发哪些异常。  
  
## <a name="syntax"></a>语法  
  
```xml  
<exception cref="member">description</exception>  
```  
  
#### <a name="parameters"></a>参数  
 `member`  
 对当前编译环境中出现的一个异常的引用。 编译器检查是否存在给定的异常，并将 `member` 转换为输出 XML 中的规范的元素名称。 `member` 必须出现在双引号 (" ") 内。  
  
 `description`  
 说明。  
  
## <a name="remarks"></a>备注  
 使用`<exception>`标记来指定可能引发哪些异常。 此标记将应用于方法定义。  
  
 使用 [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) 进行编译可以将文档注释处理到文件中。  
  
## <a name="example"></a>示例  
 此示例使用`<exception>`标记来描述异常的`IntDivide`函数可以引发。  
  
 [!code-vb[VbVbcnXmlDocComments#3](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/exception_1.vb)]  
  
## <a name="see-also"></a>请参阅  
 [XML 注释标记](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
