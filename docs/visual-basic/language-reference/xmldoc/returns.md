---
title: '&lt;返回&gt;(Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- returns XML tag
- <returns> XML tag
ms.assetid: a03a6469-d907-425d-882f-083187950e7e
ms.openlocfilehash: effc55bd65ae6c54575b7931529499505a9523cb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33598360"
---
# <a name="ltreturnsgt-visual-basic"></a>&lt;返回&gt;(Visual Basic)
指定的属性或函数的返回值。  
  
## <a name="syntax"></a>语法  
  
```xml  
<returns>description</returns>  
```  
  
#### <a name="parameters"></a>参数  
 `description`  
 返回值的说明。  
  
## <a name="remarks"></a>备注  
 使用`<returns>`方法声明来描述返回的值的注释中的标记。  
  
 使用 [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) 进行编译可以将文档注释处理到文件中。  
  
## <a name="example"></a>示例  
 此示例使用`<returns>`标记解释`DoesRecordExist`函数返回。  
  
 [!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/returns_1.vb)]  
  
## <a name="see-also"></a>请参阅  
 [XML 注释标记](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
