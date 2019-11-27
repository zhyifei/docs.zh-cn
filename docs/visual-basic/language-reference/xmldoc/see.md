---
title: <see>
ms.date: 07/20/2015
helpviewer_keywords:
- see XML tag
- <see> XML tag
ms.assetid: 7e18f60b-ef4a-4678-a797-5eb918635ca9
ms.openlocfilehash: 3c149b8ff60bcc2aba06856ad95f461fb18da4b6
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352231"
---
# <a name="see-visual-basic"></a>\<参阅 > （Visual Basic）
指定指向另一个成员的链接。  
  
## <a name="syntax"></a>语法  
  
```xml  
<see cref="member"/>  
```  
  
## <a name="parameters"></a>参数  
 `member`  
 对可从当前编译环境调用的成员或字段的引用。 编译器检查是否存在给定的码位元素，并将 `member` 传递到输出 XML 中的元素名称。 `member` 必须出现在双引号 (" ") 内。  
  
## <a name="remarks"></a>备注  
 使用 `<see>` 标记指定文本中的链接。 使用[\<seealso >](../../../visual-basic/language-reference/xmldoc/seealso.md)指示你可能希望在 "另请参阅" 部分中显示的文本。  
  
 使用 [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) 进行编译以便将文档注释处理到文件中。  
  
## <a name="example"></a>示例  
 此示例使用 `UpdateRecord` 备注 "部分中的 `<see>` 标记来引用 `DoesRecordExist` 方法。  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a>另请参阅

- [XML 注释标记](../../../visual-basic/language-reference/xmldoc/index.md)
