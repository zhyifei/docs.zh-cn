---
title: 安全和公共只读数组字段
ms.date: 03/30/2017
helpviewer_keywords:
- security [.NET Framework], public read-only array fields
ms.assetid: 3df28dee-2a9f-40ff-9852-bfdbe59c27f3
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3d36009fa4fc7b9299708768fe34a75f1fde6797
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69910735"
---
# <a name="security-and-public-read-only-array-fields"></a>安全和公共只读数组字段
永远不要使用托管库中的只读公共数组字段来定义应用程序的边界行为或安全性, 因为可以修改只读公共数组字段。  
  
## <a name="remarks"></a>备注  
 某些 .NET framework 类包含包含特定于平台的边界参数的只读公共字段。  例如, <xref:System.IO.Path.InvalidPathChars>字段是描述文件路径字符串中不允许使用的字符的数组。  在 .NET Framework 中存在许多类似的字段。  
  
 类似<xref:System.IO.Path.InvalidPathChars>公共只读字段的值可以通过代码或共享代码应用程序域的代码进行修改。  不应使用类似于这样的只读公共数组字段来定义应用程序的边界行为。  如果这样做, 恶意代码可以更改边界定义, 并以意外的方式使用您的代码。  
  
 在 .NET Framework 版本2.0 及更高版本中, 应使用返回新数组的方法, 而不是使用公共数组字段。  例如, 应<xref:System.IO.Path.GetInvalidPathChars%2A>使用方法, 而<xref:System.IO.Path.InvalidPathChars>不是使用字段。  
  
 请注意, .NET Framework 类型不使用公共字段在内部定义边界类型。  相反, .NET Framework 使用单独的私有字段。  更改这些公共字段的值不会改变 .NET Framework 类型的行为。  
  
## <a name="see-also"></a>请参阅

- [安全编码准则](../../standard/security/secure-coding-guidelines.md)
