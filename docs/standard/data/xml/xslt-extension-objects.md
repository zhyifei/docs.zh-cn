---
title: "XSLT 扩展对象"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a4ebdbad-087c-4cfe-acc0-17c48142f81a
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 18106b74c19ffdfc33176a12bec07daf2b19b17e
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2018
---
# <a name="xslt-extension-objects"></a>XSLT 扩展对象
扩展对象用于扩展样式表的功能。 扩展对象通过 <xref:System.Xml.Xsl.XsltArgumentList> 类来维护。  
  
 与使用嵌入脚本相比，使用扩展对象具有以下优点：  
  
-   改善了类的包装和重用。  
  
-   使样式表可以更小而且更容易维护。  
  
 使用 <xref:System.Xml.Xsl.XsltArgumentList> 方法将 XSLT 扩展对象添加到 <xref:System.Xml.Xsl.XsltArgumentList.AddExtensionObject%2A> 对象。 此时，限定名和命名空间 URI 与扩展对象关联。  
  
> [!NOTE]
>  调用 <xref:System.Xml.Xsl.XsltArgumentList.AddExtensionObject%2A> 方法要求具有 FullTrust 权限集。 有关详细信息，请参阅[代码访问安全性](http://msdn.microsoft.com/library/23a20143-241d-4fe5-9d9f-3933fd594c03)和 [NIB：命名权限集](http://msdn.microsoft.com/library/08250d67-c99d-4ab0-8d2b-b0e12019f6e3)。  
  
 从扩展对象返回的数据类型是四种 XPath 基本数据类型之一：`number`、`string`、`Boolean` 和 `node set`。  
  
 任何使用 `params` 关键字定义的方法允许传递未指定的参数数目，<xref:System.Xml.Xsl.XslCompiledTransform> 类目前不支持。 利用通过 `params` 关键字定义的方法的 XSLT 样式表也无法正确使用。 有关详细信息，请参阅 [params](~/docs/csharp/language-reference/keywords/params.md)。  
  
### <a name="to-use-an-xslt-extension-object"></a>使用 XSLT 扩展对象  
  
1.  创建 <xref:System.Xml.Xsl.XsltArgumentList> 对象并使用 <xref:System.Xml.Xsl.XsltArgumentList.AddExtensionObject%2A> 方法添加扩展对象。  
  
2.  从样式表调用扩展对象。  
  
3.  将 <xref:System.Xml.Xsl.XsltArgumentList> 对象传递给 <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> 方法。  
  
## <a name="see-also"></a>请参阅  
 [XSLT 转换](../../../../docs/standard/data/xml/xslt-transformations.md)  
 [XSLT 安全注意事项](../../../../docs/standard/data/xml/xslt-security-considerations.md)
