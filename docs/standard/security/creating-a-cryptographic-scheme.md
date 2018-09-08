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
ms.openlocfilehash: 2db6d4229ac777801aff792c86fe0e5e9a1b4994
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/08/2018
ms.locfileid: "44197888"
---
# <a name="creating-a-cryptographic-scheme"></a><span data-ttu-id="6ca74-102">创建加密方案</span><span class="sxs-lookup"><span data-stu-id="6ca74-102">Creating a Cryptographic Scheme</span></span>
<span data-ttu-id="6ca74-103">可结合使用 .NET Framework 的加密组件来创建不同的方案，以加密和解密数据。</span><span class="sxs-lookup"><span data-stu-id="6ca74-103">The cryptographic components of the .NET Framework can be combined to create different schemes to encrypt and decrypt data.</span></span>  
  
 <span data-ttu-id="6ca74-104">用于加密和解密数据的简单加密方案可能指定以下步骤：</span><span class="sxs-lookup"><span data-stu-id="6ca74-104">A simple cryptographic scheme for encrypting and decrypting data might specify the following steps:</span></span>  
  
1.  <span data-ttu-id="6ca74-105">每个参与方均生成一个公钥/私钥对。</span><span class="sxs-lookup"><span data-stu-id="6ca74-105">Each party generates a public/private key pair.</span></span>  
  
2.  <span data-ttu-id="6ca74-106">双方交换各自的公钥。</span><span class="sxs-lookup"><span data-stu-id="6ca74-106">The parties exchange their public keys.</span></span>  
  
3.  <span data-ttu-id="6ca74-107">例如，每个参与方均生成一个用于加密 TripleDES 的密钥，并使用对方的公钥对新创建的密钥进行加密。</span><span class="sxs-lookup"><span data-stu-id="6ca74-107">Each party generates a secret key for TripleDES encryption, for example, and encrypts the newly created key using the other's public key.</span></span>  
  
4.  <span data-ttu-id="6ca74-108">每个参与方都将数据发送给另一方，并以特定的顺序将对方的密钥与自身的密钥相结合，以创建新密钥。</span><span class="sxs-lookup"><span data-stu-id="6ca74-108">Each party sends the data to the other and combines the other's secret key with its own, in a particular order, to create a new secret key.</span></span>  
  
5.  <span data-ttu-id="6ca74-109">然后，双方使用对称加密启动一个对话。</span><span class="sxs-lookup"><span data-stu-id="6ca74-109">The parties then initiate a conversation using symmetric encryption.</span></span>  
  
 <span data-ttu-id="6ca74-110">创建加密方案是一项重要任务。</span><span class="sxs-lookup"><span data-stu-id="6ca74-110">Creating a cryptographic scheme is not a trivial task.</span></span> <span data-ttu-id="6ca74-111">有关使用加密的详细信息，请参阅处平台 SDK 文档中的加密主题 http://msdn.microsoft.com/library 。</span><span class="sxs-lookup"><span data-stu-id="6ca74-111">For more information on using cryptography, see the Cryptography topic in the Platform SDK documentation at http://msdn.microsoft.com/library.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ca74-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="6ca74-112">See also</span></span>

- [<span data-ttu-id="6ca74-113">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="6ca74-113">Cryptographic Services</span></span>](../../../docs/standard/security/cryptographic-services.md)
