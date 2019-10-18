---
title: <see> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- see XML tag
- <see> XML tag
ms.assetid: 7e18f60b-ef4a-4678-a797-5eb918635ca9
ms.openlocfilehash: e3ae5fb63540e47e5b8da2e2d60d5bd736e019d7
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524657"
---
# <a name="see-visual-basic"></a>\<see > （Visual Basic）
指定指向另一个成员的链接。  
  
## <a name="syntax"></a>语法  
  
```xml  
<see cref="member"/>  
```  
  
## <a name="parameters"></a>参数  
 `member`  
 对可从当前编译环境调用的成员或字段的引用。 编译器检查是否存在给定的码位元素，并将 `member` 传递到输出 XML 中的元素名称。 `member` 必须出现在双引号 (" ") 内。  
  
## <a name="remarks"></a>备注  
 使用 `<see>` 标记指定文本中的链接。 使用[\<seealso >](../../../visual-basic/language-reference/xmldoc/seealso.md)来指示你可能希望在 "另请参阅" 部分中显示的文本。  
  
 使用 [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) 进行编译以便将文档注释处理到文件中。  
  
## <a name="example"></a>示例  
 此示例使用 `UpdateRecord` 备注 "部分中的 `<see>` 标记来引用 `DoesRecordExist` 方法。  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a>请参阅

- [XML 注释标记](../../../visual-basic/language-reference/xmldoc/index.md)
