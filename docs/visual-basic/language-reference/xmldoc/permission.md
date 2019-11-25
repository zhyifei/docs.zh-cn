---
title: <permission>
ms.date: 07/20/2015
helpviewer_keywords:
- <permission> XML tag
- permission XML tag
ms.assetid: 0edf0500-5cd7-49c0-9255-64c48f972b77
ms.openlocfilehash: 71b00b669804e644d1171480192b9d55455bdf53
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352266"
---
# <a name="permission-visual-basic"></a>\<permission> (Visual Basic)
Specifies a required permission for the member.  
  
## <a name="syntax"></a>语法  
  
```xml  
<permission cref="member">description</permission>  
```  
  
## <a name="parameters"></a>参数  
 `member`  
 对可从当前编译环境调用的成员或字段的引用。 编译器检查是否存在给定的代码元素，并将 `member` 转换为输出 XML 中规范的元素名称。 Enclose `member` in quotation marks (" ").  
  
 `description`  
 对成员访问权限的说明。  
  
## <a name="remarks"></a>备注  
 Use the `<permission>` tag to document the access of a member. Use the <xref:System.Security.PermissionSet> class to specify access to a member.  
  
 使用 [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) 进行编译以便将文档注释处理到文件中。  
  
## <a name="example"></a>示例  
 This example uses the `<permission>` tag to describe that the <xref:System.Security.Permissions.FileIOPermission> is required by the `ReadFile` method.  
  
 [!code-vb[VbVbcnXmlDocComments#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#7)]  
  
## <a name="see-also"></a>请参阅

- [XML 注释标记](../../../visual-basic/language-reference/xmldoc/index.md)
