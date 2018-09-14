---
title: 使用哈希代码确保数据完整性
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- generating hash
- verifying hash codes
- cryptography [.NET Framework], hash
- data integrity
- checking hash codes
- encryption [.NET Framework], hash
- hash
ms.assetid: 33660f33-b70f-4dca-8c87-ab35cfc2961a
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 16770ea938973372d1d94c628c42d5d5bf10c695
ms.sourcegitcommit: 76a304c79a32aa13889ebcf4b9789a4542b48e3e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/13/2018
ms.locfileid: "45528547"
---
# <a name="ensuring-data-integrity-with-hash-codes"></a><span data-ttu-id="59b5a-102">使用哈希代码确保数据完整性</span><span class="sxs-lookup"><span data-stu-id="59b5a-102">Ensuring Data Integrity with Hash Codes</span></span>
<span data-ttu-id="59b5a-103">哈希值是用于唯一标识数据的固定长度的数字值。</span><span class="sxs-lookup"><span data-stu-id="59b5a-103">A hash value is a numeric value of a fixed length that uniquely identifies data.</span></span> <span data-ttu-id="59b5a-104">哈希值以小得多的数字值表示大量数据，因此与数字签名配合使用。</span><span class="sxs-lookup"><span data-stu-id="59b5a-104">Hash values represent large amounts of data as much smaller numeric values, so they are used with digital signatures.</span></span> <span data-ttu-id="59b5a-105">对哈希值进行签名比对较大的值进行签名更为高效。</span><span class="sxs-lookup"><span data-stu-id="59b5a-105">You can sign a hash value more efficiently than signing the larger value.</span></span> <span data-ttu-id="59b5a-106">对于验证通过不安全通道发送的数据的完整性，哈希值也很有用。</span><span class="sxs-lookup"><span data-stu-id="59b5a-106">Hash values are also useful for verifying the integrity of data sent through insecure channels.</span></span> <span data-ttu-id="59b5a-107">当被发送出去确定数据是否已更改时，将接收数据的哈希值与数据的哈希值相比较。</span><span class="sxs-lookup"><span data-stu-id="59b5a-107">The hash value of received data can be compared to the hash value of data as it was sent to determine whether the data was altered.</span></span>  
  
 <span data-ttu-id="59b5a-108">本主题介绍如何通过使用 <xref:System.Security.Cryptography?displayProperty=nameWithType> 命名空间中的类生成和验证哈希代码。</span><span class="sxs-lookup"><span data-stu-id="59b5a-108">This topic describes how to generate and verify hash codes by using the classes in the <xref:System.Security.Cryptography?displayProperty=nameWithType> namespace.</span></span>  
  
## <a name="generating-a-hash"></a><span data-ttu-id="59b5a-109">生成哈希</span><span class="sxs-lookup"><span data-stu-id="59b5a-109">Generating a Hash</span></span>  
 <span data-ttu-id="59b5a-110">托管哈希类可以对字节数组或托管流对象进行哈希处理。</span><span class="sxs-lookup"><span data-stu-id="59b5a-110">The managed hash classes can hash either an array of bytes or a managed stream object.</span></span> <span data-ttu-id="59b5a-111">以下示例使用 SHA1 哈希算法为字符串创建哈希值。</span><span class="sxs-lookup"><span data-stu-id="59b5a-111">The following example uses the SHA1 hash algorithm to create a hash value for a string.</span></span> <span data-ttu-id="59b5a-112">该示例使用 <xref:System.Text.UnicodeEncoding> 类将字符串转换为通过使用 <xref:System.Security.Cryptography.SHA1Managed> 类进行哈希处理的字节数组。</span><span class="sxs-lookup"><span data-stu-id="59b5a-112">The example uses the <xref:System.Text.UnicodeEncoding> class to convert the string into an array of bytes that are hashed by using the <xref:System.Security.Cryptography.SHA1Managed> class.</span></span> <span data-ttu-id="59b5a-113">然后向控制台显示哈希值。</span><span class="sxs-lookup"><span data-stu-id="59b5a-113">The hash value is then displayed to the console.</span></span>  
  
 [!code-csharp[GeneratingAHash#1](../../../samples/snippets/csharp/VS_Snippets_CLR/generatingahash/cs/program.cs#1)]
 [!code-vb[GeneratingAHash#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/generatingahash/vb/program.vb#1)]  
  
 <span data-ttu-id="59b5a-114">此代码将向控制台显示以下字符串：</span><span class="sxs-lookup"><span data-stu-id="59b5a-114">This code will display the following string to the console:</span></span>  
  
 `59 4 248 102 77 97 142 201 210 12 224 93 25 41 100 197 213 134 130 135`  
  
## <a name="verifying-a-hash"></a><span data-ttu-id="59b5a-115">验证哈希</span><span class="sxs-lookup"><span data-stu-id="59b5a-115">Verifying a Hash</span></span>  
 <span data-ttu-id="59b5a-116">可将数据与哈希值进行比较，以确定其完整性。</span><span class="sxs-lookup"><span data-stu-id="59b5a-116">Data can be compared to a hash value to determine its integrity.</span></span> <span data-ttu-id="59b5a-117">通常，在某个特定时间对数据进行哈希运算，并以某种方式保护哈希值。</span><span class="sxs-lookup"><span data-stu-id="59b5a-117">Usually, data is hashed at a certain time and the hash value is protected in some way.</span></span> <span data-ttu-id="59b5a-118">稍后，可以再次对数据进行哈希运算，并与受保护的值进行比较。</span><span class="sxs-lookup"><span data-stu-id="59b5a-118">At a later time, the data can be hashed again and compared to the protected value.</span></span> <span data-ttu-id="59b5a-119">如果哈希值匹配，则数据未更改。</span><span class="sxs-lookup"><span data-stu-id="59b5a-119">If the hash values match, the data has not been altered.</span></span> <span data-ttu-id="59b5a-120">如果值不匹配，则数据已损坏。</span><span class="sxs-lookup"><span data-stu-id="59b5a-120">If the values do not match, the data has been corrupted.</span></span> <span data-ttu-id="59b5a-121">要使此系统发挥作用，必须对受保护的哈希加密或对所有的不受信任方保密。</span><span class="sxs-lookup"><span data-stu-id="59b5a-121">For this system to work, the protected hash must be encrypted or kept secret from all untrusted parties.</span></span>  
  
 <span data-ttu-id="59b5a-122">以下示例将字符串旧的哈希值与新的哈希值进行比较。</span><span class="sxs-lookup"><span data-stu-id="59b5a-122">The following example compares the previous hash value of a string to a new hash value.</span></span> <span data-ttu-id="59b5a-123">此示例循环访问哈希值的每个字节并进行比较。</span><span class="sxs-lookup"><span data-stu-id="59b5a-123">This example loops through each byte of the hash values and makes a comparison.</span></span>  
  
 [!code-csharp[VerifyingAHash#1](../../../samples/snippets/csharp/VS_Snippets_CLR/verifyingahash/cs/program.cs#1)]
 [!code-vb[VerifyingAHash#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/verifyingahash/vb/program.vb#1)]  
  
 <span data-ttu-id="59b5a-124">如果两个哈希值匹配，则此代码将向控制台现实以下内容：</span><span class="sxs-lookup"><span data-stu-id="59b5a-124">If the two hash values match, this code displays the following to the console:</span></span>  
  
```  
The hash codes match.  
```  
  
 <span data-ttu-id="59b5a-125">如果不匹配，则此代码显示以下信息：</span><span class="sxs-lookup"><span data-stu-id="59b5a-125">If they do not match, the code displays the following:</span></span>  
  
```  
The hash codes do not match.  
```  
  
## <a name="see-also"></a><span data-ttu-id="59b5a-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="59b5a-126">See also</span></span>

- [<span data-ttu-id="59b5a-127">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="59b5a-127">Cryptographic Services</span></span>](../../../docs/standard/security/cryptographic-services.md)
