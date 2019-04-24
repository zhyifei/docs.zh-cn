---
title: 创建加密方案
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- encryption [.NET Framework], creating cryptographic schemes
- cryptography [.NET Framework], creating cryptographic schemes
ms.assetid: d40c509f-5a5e-46cc-94cb-a951e9ab6843
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3ef3741ef5cec720c2fb285c9aa60d610acc0be9
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59321648"
---
# <a name="creating-a-cryptographic-scheme"></a>创建加密方案
可结合使用 .NET Framework 的加密组件来创建不同的方案，以加密和解密数据。  
  
 用于加密和解密数据的简单加密方案可能指定以下步骤：  
  
1. 每个参与方均生成一个公钥/私钥对。  
  
2. 双方交换各自的公钥。  
  
3. 例如，每个参与方均生成一个用于加密 TripleDES 的密钥，并使用对方的公钥对新创建的密钥进行加密。  
  
4. 每个参与方都将数据发送给另一方，并以特定的顺序将对方的密钥与自身的密钥相结合，以创建新密钥。  
  
5. 然后，双方使用对称加密启动一个对话。  
  
 创建加密方案是一项重要任务。
  
## <a name="see-also"></a>请参阅

- [Cryptographic Services](../../../docs/standard/security/cryptographic-services.md)
