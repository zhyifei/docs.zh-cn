---
title: <returns> （Visual Basic）
ms.date: 07/20/2015
helpviewer_keywords:
- returns XML tag
- <returns> XML tag
ms.assetid: a03a6469-d907-425d-882f-083187950e7e
ms.openlocfilehash: b220c2a9aa544413c3692485f6c1eb2b64e54389
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524680"
---
# <a name="returns-visual-basic"></a>\<returns > （Visual Basic）
指定属性或函数的返回值。  
  
## <a name="syntax"></a>语法  
  
```xml  
<returns>description</returns>  
```  
  
## <a name="parameters"></a>参数  
 `description`  
 返回值的说明。  
  
## <a name="remarks"></a>备注  
 在方法声明的注释中使用 `<returns>` 标记来描述返回值。  
  
 使用 [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) 进行编译以便将文档注释处理到文件中。  
  
## <a name="example"></a>示例  
 此示例使用 `<returns>` 标记解释 `DoesRecordExist` 函数返回的内容。  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a>请参阅

- [XML 注释标记](../../../visual-basic/language-reference/xmldoc/index.md)
