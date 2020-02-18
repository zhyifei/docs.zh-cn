---
title: 安全和公共只读数组字段
ms.date: 03/30/2017
helpviewer_keywords:
- security [.NET Framework], public read-only array fields
ms.assetid: 3df28dee-2a9f-40ff-9852-bfdbe59c27f3
ms.openlocfilehash: 215e8136b4bc3f2982cdb2d8382b0eca6a881f9b
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2020
ms.locfileid: "77217033"
---
# <a name="security-and-public-read-only-array-fields"></a>安全和公共只读数组字段
永远不要使用托管库中的只读公共数组字段来定义应用程序的边界行为或安全性，因为可以修改只读公共数组字段。  
  
## <a name="remarks"></a>备注  
 某些 .NET framework 类包含包含特定于平台的边界参数的只读公共字段。  例如，"<xref:System.IO.Path.InvalidPathChars>" 字段是描述文件路径字符串中不允许的字符的数组。  在 .NET Framework 中存在许多类似的字段。  
  
 公共只读字段（如 <xref:System.IO.Path.InvalidPathChars>）的值可以通过代码或共享代码应用程序域的代码进行修改。  不应使用类似于这样的只读公共数组字段来定义应用程序的边界行为。  如果这样做，恶意代码可以更改边界定义，并以意外的方式使用您的代码。  
  
 在 .NET Framework 版本2.0 及更高版本中，应使用返回新数组的方法，而不是使用公共数组字段。  例如，你应该使用 <xref:System.IO.Path.GetInvalidPathChars%2A> 方法，而不是使用 <xref:System.IO.Path.InvalidPathChars> 字段。  
  
 请注意，.NET Framework 类型不使用公共字段在内部定义边界类型。  相反，.NET Framework 使用单独的私有字段。  更改这些公共字段的值不会改变 .NET Framework 类型的行为。  
  
## <a name="see-also"></a>另请参阅

- [安全编码准则](../../standard/security/secure-coding-guidelines.md)
