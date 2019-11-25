---
title: <remarks>
ms.date: 07/20/2015
helpviewer_keywords:
- <remarks> XML tag
- remarks XML tag
ms.assetid: c6241773-a7ed-41c9-9a8b-9722a0c606a9
ms.openlocfilehash: b327e548bcdce1522a888855bd88e3150695147b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352251"
---
# <a name="remarks-visual-basic"></a>\<remarks> (Visual Basic)
Specifies a remarks section for the member.  
  
## <a name="syntax"></a>语法  
  
```xml  
<remarks>description</remarks>  
```  
  
## <a name="parameters"></a>参数  
 `description`  
 对成员的说明。  
  
## <a name="remarks"></a>备注  
 Use the `<remarks>` tag to add information about a type, supplementing the information specified with [\<summary>](../../../visual-basic/language-reference/xmldoc/summary.md).  
  
 This information appears in the Object Browser. For information about the Object Browser, see [Viewing the Structure of Code](/visualstudio/ide/viewing-the-structure-of-code).  
  
 使用 [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) 进行编译以便将文档注释处理到文件中。  
  
## <a name="example"></a>示例  
 This example uses the `<remarks>` tag to explain what the `UpdateRecord` method does.  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a>请参阅

- [XML 注释标记](../../../visual-basic/language-reference/xmldoc/index.md)
