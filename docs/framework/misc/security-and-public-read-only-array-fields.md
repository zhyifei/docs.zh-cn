---
title: "安全和公共只读数组字段"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: security [.NET Framework], public read-only array fields
ms.assetid: 3df28dee-2a9f-40ff-9852-bfdbe59c27f3
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d86d054d3a5a4e10b8efcc3292f3a18ea37f9b87
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="security-and-public-read-only-array-fields"></a>安全和公共只读数组字段
切勿使用托管库的公共的只读数组字段来定义的边界行为或应用程序的安全，因为可以修改只读公共数组字段。  
  
## <a name="remarks"></a>备注  
 一些.NET framework 类包括只读包含特定于平台的边界参数的公共字段。  例如，<xref:System.IO.Path.InvalidPathChars>字段是一个数组，其中描述的文件路径字符串中不允许使用的字符。  许多类似的字段会显示整个.NET Framework。  
  
 公共只读字段的值喜欢<xref:System.IO.Path.InvalidPathChars>可通过你的代码或共享代码的应用程序域的代码修改。  不应使用如下公共的只读数组字段来定义你的应用程序的边界行为。  如果这样做，恶意代码可以修改的边界定义，以意想不到的方式使用您的代码。  
  
 在版本 2.0 及更高版本的.NET Framework 中，应使用返回一个新数组，而不是使用公共数组字段的方法。  例如，而不是使用<xref:System.IO.Path.InvalidPathChars>字段中，你应使用<xref:System.IO.Path.GetInvalidPathChars%2A>方法。  
  
 请注意，.NET Framework 类型并不使用公共字段内部定义边界类型。  相反，.NET Framework 使用单独的私有字段。  更改这些公共字段的值不会更改.NET Framework 类型的行为。  
  
## <a name="see-also"></a>请参阅  
 [安全编码准则](../../../docs/standard/security/secure-coding-guidelines.md)
