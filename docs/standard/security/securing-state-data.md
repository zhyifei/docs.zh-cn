---
title: 保护状态数据
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- security [.NET Framework], state data
- code security, state data
- secure coding, state data
- state data security
ms.assetid: 12671309-2877-43fe-a3df-6863507e712d
author: mairaw
ms.author: mairaw
ms.openlocfilehash: fe941fff7091fb579e41a3c417dbb2129bcf3e8c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33580778"
---
# <a name="securing-state-data"></a>保护状态数据
处理敏感数据或做出任何种类的安全决策的应用程序需要将相关数据保持在自己的控制之下，而不允许其他可能的恶意代码直接访问这些数据。 保护内存中的数据的最好方法就是，将数据声明为私有或内部（范围限定为相同的程序集内）变量。 然而，即使这些数据受到访问权制约，你也应当注意：  
  
-   通过使用反射机制，那些能够引用你的对象的、高度受信任的代码可以获取和设置私有成员。  
  
-   使用序列化时，如果高度受信任的代码可以访问序列化形式的对象中的相应数据，那么它就可以有效地获取和设置私有成员。  
  
-   调试时，可以读取这些数据。  
  
 千万不要让你自己的任何方法或属性在无意中公开这些值。  
  
## <a name="see-also"></a>请参阅  
 [安全编码准则](../../../docs/standard/security/secure-coding-guidelines.md)
