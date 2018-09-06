---
title: 计时漏洞 CBC 模式下使用填充的对称解密
description: 了解如何检测和缓解与使用填充的密码块链 (CBC) 模式下对称解密计时漏洞。
ms.date: 06/12/2018
author: blowdart
ms.author: mairaw
ms.openlocfilehash: 6d16b6849bfd4744f1828cda38a537f842243c1d
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2018
ms.locfileid: "43881364"
---
# <a name="timing-vulnerabilities-with-cbc-mode-symmetric-decryption-using-padding"></a><span data-ttu-id="a1c46-103">计时漏洞 CBC 模式下使用填充的对称解密</span><span class="sxs-lookup"><span data-stu-id="a1c46-103">Timing vulnerabilities with CBC-mode symmetric decryption using padding</span></span>

<span data-ttu-id="a1c46-104">Microsoft 认为是不再安全而无需首先除确保完整性的密码文本，已应用可验证填充时使用对称加密的密码块链 (CBC) 模式加密的数据进行解密非常具体情况。</span><span class="sxs-lookup"><span data-stu-id="a1c46-104">Microsoft believes that it's no longer safe to decrypt data encrypted with the Cipher-Block-Chaining (CBC) mode of symmetric encryption when verifiable padding has been applied without first ensuring the integrity of the ciphertext, except for very specific circumstances.</span></span> <span data-ttu-id="a1c46-105">此判断基于当前已知加密研究。</span><span class="sxs-lookup"><span data-stu-id="a1c46-105">This judgement is based on currently known cryptographic research.</span></span> 

## <a name="introduction"></a><span data-ttu-id="a1c46-106">介绍</span><span class="sxs-lookup"><span data-stu-id="a1c46-106">Introduction</span></span>

<span data-ttu-id="a1c46-107">填充 oracle 攻击是一种攻击可让攻击者不知道该密钥解密数据的内容的加密数据。</span><span class="sxs-lookup"><span data-stu-id="a1c46-107">A padding oracle attack is a type of attack against encrypted data that allows the attacker to decrypt the contents of the data, without knowing the key.</span></span>

<span data-ttu-id="a1c46-108">Oracle 是指"告诉"它为提供了有关他们正在执行的操作是否是正确的攻击者信息。</span><span class="sxs-lookup"><span data-stu-id="a1c46-108">An oracle refers to a "tell" which gives an attacker information about whether the action they're executing is correct or not.</span></span> <span data-ttu-id="a1c46-109">假设播放看板或具有一个子卡游戏。</span><span class="sxs-lookup"><span data-stu-id="a1c46-109">Imagine playing a board or card game with a child.</span></span> <span data-ttu-id="a1c46-110">当她人脸点亮用大笑脸因为她认为她即将进行一个好办法，即 oracle。</span><span class="sxs-lookup"><span data-stu-id="a1c46-110">When her face lights up with a big smile because she thinks she's about to make a good move, that's an oracle.</span></span> <span data-ttu-id="a1c46-111">作为对手，可用于此 oracle 进行适当规划下一步移动。</span><span class="sxs-lookup"><span data-stu-id="a1c46-111">You, as the opponent, can use this oracle to plan your next move appropriately.</span></span>

<span data-ttu-id="a1c46-112">填充是一个特定的加密术语。</span><span class="sxs-lookup"><span data-stu-id="a1c46-112">Padding is a specific cryptographic term.</span></span> <span data-ttu-id="a1c46-113">某些加密法，是使用对数据进行加密的算法，处理其中每个块的大小是固定的数据块。</span><span class="sxs-lookup"><span data-stu-id="a1c46-113">Some ciphers, which are the algorithms used to encrypt your data, work on blocks of data where each block is a fixed size.</span></span> <span data-ttu-id="a1c46-114">如果您想要加密的数据不是适当的大小以填充块，直到它填充你的数据。</span><span class="sxs-lookup"><span data-stu-id="a1c46-114">If the data you want to encrypt isn't the right size to fill the blocks, your data is padded until it does.</span></span> <span data-ttu-id="a1c46-115">许多形式的填充要求，填充始终是存在，即使原始输入是适当大小。</span><span class="sxs-lookup"><span data-stu-id="a1c46-115">Many forms of padding require that padding to always be present, even if the original input was of the right size.</span></span> <span data-ttu-id="a1c46-116">这样，要始终安全地删除后解密的填充。</span><span class="sxs-lookup"><span data-stu-id="a1c46-116">This allows the padding to always be safely removed upon decryption.</span></span>

<span data-ttu-id="a1c46-117">将两件事放在一起，显示已解密的数据是否具有有效的填充量与填充 oracle 软件实现。</span><span class="sxs-lookup"><span data-stu-id="a1c46-117">Putting the two things together, a software implementation with a padding oracle reveals whether decrypted data has valid padding.</span></span> <span data-ttu-id="a1c46-118">Oracle 可能是很简单，例如返回一个值，显示"填充无效"或类似于获取很显著不同的时间来处理而不是无效的块是有效块更复杂的内容。</span><span class="sxs-lookup"><span data-stu-id="a1c46-118">The oracle could be something as simple as returning a value that says "Invalid padding" or something more complicated like taking a measurably different time to process a valid block as opposed to an invalid block.</span></span>

<span data-ttu-id="a1c46-119">基于块加密法具有另一个属性，名为模式，它决定了第二个块中的数据的第一个块中的数据的关系，等等。</span><span class="sxs-lookup"><span data-stu-id="a1c46-119">Block-based ciphers have another property, called the mode, which determines the relationship of data in the first block to the data in the second block, and so on.</span></span> <span data-ttu-id="a1c46-120">CBC 最常使用的模式之一。</span><span class="sxs-lookup"><span data-stu-id="a1c46-120">One of the most commonly used modes is CBC.</span></span> <span data-ttu-id="a1c46-121">CBC 引入了一个初始的随机块，已知为初始化向量 (IV)，并将前一个块组合与静态加密，以使其以便对相同消息使用相同的密钥进行加密并不始终生成相同的加密的输出的结果。</span><span class="sxs-lookup"><span data-stu-id="a1c46-121">CBC introduces an initial random block, known as the Initialization Vector (IV), and combines the previous block with the result of static encryption to make it such that encrypting the same message with the same key doesn't always produce the same encrypted output.</span></span>

<span data-ttu-id="a1c46-122">攻击者可以使用填充 oracle，结合 CBC 数据结构化、 将略有更改的消息发送到公开 oracle，代码并保留发送的数据直到 oracle 会告知他们数据正确。</span><span class="sxs-lookup"><span data-stu-id="a1c46-122">An attacker can use a padding oracle, in combination with how CBC data is structured, to send slightly changed messages to the code that exposes the oracle, and keep sending data until the oracle tells them the data is correct.</span></span> <span data-ttu-id="a1c46-123">此响应中，攻击者可以解密该消息逐字节。</span><span class="sxs-lookup"><span data-stu-id="a1c46-123">From this response, the attacker can decrypt the message byte by byte.</span></span>

<span data-ttu-id="a1c46-124">现代计算机网络是此类高质量的攻击者可以检测非常小 （小于 0.1 毫秒） 在远程系统上执行之间的差异的时间。</span><span class="sxs-lookup"><span data-stu-id="a1c46-124">Modern computer networks are of such high quality that an attacker can detect very small (less than 0.1 ms) differences in execution time on remote systems.</span></span> <span data-ttu-id="a1c46-125">数据未被篡改后才会发生解密成功，即假定的应用程序可能易受到攻击从工具，可用于观察成功和不成功解密的差异。</span><span class="sxs-lookup"><span data-stu-id="a1c46-125">Applications that are assuming that a successful decryption can only happen when the data wasn't tampered with may be vulnerable to attack from tools that are designed to observe differences in successful and unsuccessful decryption.</span></span> <span data-ttu-id="a1c46-126">尽管这种计时差异可能在某些语言或库比其他更重要，现在认为这是对所有语言和库的实际威胁时考虑到故障的应用程序的响应。</span><span class="sxs-lookup"><span data-stu-id="a1c46-126">While this timing difference may be more significant in some languages or libraries than others, it's now believed that this is a practical threat for all languages and libraries when the application's response to failure is taken into account.</span></span>

<span data-ttu-id="a1c46-127">这种攻击依赖于更改加密的数据和测试结果与 oracle 的能力。</span><span class="sxs-lookup"><span data-stu-id="a1c46-127">This attack relies on the ability to change the encrypted data and test the result with the oracle.</span></span> <span data-ttu-id="a1c46-128">完全缓解攻击的唯一方法是检测到加密的数据更改，并拒绝对其执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="a1c46-128">The only way to fully mitigate the attack is to detect changes to the encrypted data and refuse to perform any actions on it.</span></span> <span data-ttu-id="a1c46-129">若要执行此操作的标准方法是创建数据的签名和执行任何操作之前来验证该签名。</span><span class="sxs-lookup"><span data-stu-id="a1c46-129">The standard way to do this is to create a signature for the data and validate that signature before any operations are performed.</span></span> <span data-ttu-id="a1c46-130">签名必须是可验证，攻击者无法创建，否则为他们会更改加密的数据，然后计算基于已更改的数据的新签名。</span><span class="sxs-lookup"><span data-stu-id="a1c46-130">The signature must be verifiable, it cannot be created by the attacker, otherwise they'd change the encrypted data, then compute a new signature based on the changed data.</span></span> <span data-ttu-id="a1c46-131">一种常见类型的适当的签名被称为键控哈希消息身份验证代码 (HMAC)。</span><span class="sxs-lookup"><span data-stu-id="a1c46-131">One common type of appropriate signature is known as a keyed-hash message authentication code (HMAC).</span></span> <span data-ttu-id="a1c46-132">它采用机密密钥，仅对生成 HMAC 的用户并向其进行验证的人员已知，HMAC 不同于校验和。</span><span class="sxs-lookup"><span data-stu-id="a1c46-132">An HMAC differs from a checksum in that it takes a secret key, known only to the person producing the HMAC and to the person validating it.</span></span> <span data-ttu-id="a1c46-133">而无需拥有密钥，无法生成正确的 HMAC。</span><span class="sxs-lookup"><span data-stu-id="a1c46-133">Without possession of the key, you can't produce a correct HMAC.</span></span> <span data-ttu-id="a1c46-134">收到你的数据，需要加密的数据，你和发件人共享，然后比较它们根据一个向你发送的 HMAC 计算独立计算 HMAC 使用机密密钥。</span><span class="sxs-lookup"><span data-stu-id="a1c46-134">When you receive your data, you'd take the encrypted data, independently compute the HMAC using the secret key you and the sender share, then compare the HMAC they sent against the one you computed.</span></span> <span data-ttu-id="a1c46-135">这种比较必须是常量时间内，否则添加另一种可检测 oracle 允许不同类型的攻击。</span><span class="sxs-lookup"><span data-stu-id="a1c46-135">This comparison must be constant time, otherwise you've added another detectable oracle, allowing a different type of attack.</span></span>

<span data-ttu-id="a1c46-136">总之，若要使用请安全地填充 CBC 块加密法，必须将它们组合使用 HMAC （或另一个数据完整性检查），用于验证之前尝试使用常量时间内比较对数据进行解密。</span><span class="sxs-lookup"><span data-stu-id="a1c46-136">In summary, to use padded CBC block ciphers safely, you must combine them with an HMAC (or another data integrity check) that you validate using a constant time comparison before trying to decrypt the data.</span></span> <span data-ttu-id="a1c46-137">由于所有更改后的消息需要相同的长时间，以生成响应，则会阻止攻击。</span><span class="sxs-lookup"><span data-stu-id="a1c46-137">Since all altered messages take the same amount time to produce a response, the attack is prevented.</span></span>

## <a name="who-is-vulnerable"></a><span data-ttu-id="a1c46-138">谁是易受攻击</span><span class="sxs-lookup"><span data-stu-id="a1c46-138">Who is vulnerable</span></span>

<span data-ttu-id="a1c46-139">此漏洞适用于托管和本机应用程序执行其自己的加密和解密。</span><span class="sxs-lookup"><span data-stu-id="a1c46-139">This vulnerability applies to both managed and native applications that are performing their own encryption and decryption.</span></span> <span data-ttu-id="a1c46-140">这包括，例如：</span><span class="sxs-lookup"><span data-stu-id="a1c46-140">This includes, for example:</span></span>

- <span data-ttu-id="a1c46-141">应用程序，对更高版本的服务器上解密 cookie 进行加密。</span><span class="sxs-lookup"><span data-stu-id="a1c46-141">An application that encrypts a cookie for later decryption on the server.</span></span>
- <span data-ttu-id="a1c46-142">更高版本解密提供其列的用户将数据插入表中的功能的数据库应用程序。</span><span class="sxs-lookup"><span data-stu-id="a1c46-142">A database application that provides the ability for users to insert data into a table whose columns are later decrypted.</span></span>
- <span data-ttu-id="a1c46-143">将数据传输应用程序依赖于使用共享的密钥来保护传输中的数据的加密。</span><span class="sxs-lookup"><span data-stu-id="a1c46-143">A data transfer application that relies on encryption using a shared key to protect the data in transit.</span></span>
- <span data-ttu-id="a1c46-144">应用程序进行加密和解密"内部"TLS 隧道的消息。</span><span class="sxs-lookup"><span data-stu-id="a1c46-144">An application that encrypts and decrypts messages "inside" the TLS tunnel.</span></span>

<span data-ttu-id="a1c46-145">请注意，使用单独的 TLS 可能不保护您在这些情况下。</span><span class="sxs-lookup"><span data-stu-id="a1c46-145">Note that using TLS alone may not protect you in these scenarios.</span></span>

<span data-ttu-id="a1c46-146">易受攻击的应用程序：</span><span class="sxs-lookup"><span data-stu-id="a1c46-146">A vulnerable application:</span></span>

- <span data-ttu-id="a1c46-147">可验证的填充模式中，如 PKCS #7 或 ANSI X.923 使用 CBC 密码模式解密数据。</span><span class="sxs-lookup"><span data-stu-id="a1c46-147">Decrypts data using the CBC cipher mode with a verifiable padding mode, such as PKCS#7 or ANSI X.923.</span></span>
- <span data-ttu-id="a1c46-148">不执行数据完整性检查 （通过在 MAC 或非对称的数字签名） 的情况下执行解密。</span><span class="sxs-lookup"><span data-stu-id="a1c46-148">Performs the decryption without having performed a data integrity check (via a MAC or an asymmetric digital signature).</span></span>

<span data-ttu-id="a1c46-149">这同样适用于基于抽象这些基元，例如，加密消息语法 (PKCS #7/CMS) EnvelopedData 结构的基础上构建的应用程序。</span><span class="sxs-lookup"><span data-stu-id="a1c46-149">This also applies to applications built on top of abstractions over top of these primitives, such as the Cryptographic Message Syntax (PKCS#7/CMS) EnvelopedData structure.</span></span>

## <a name="related-areas-of-concern"></a><span data-ttu-id="a1c46-150">相关的关注区域</span><span class="sxs-lookup"><span data-stu-id="a1c46-150">Related areas of concern</span></span>

<span data-ttu-id="a1c46-151">研究促使 Microsoft 进一步关心 CBC 用 ISO 10126 等效项填充该消息具有已知或可预测的页脚结构时填充的消息。</span><span class="sxs-lookup"><span data-stu-id="a1c46-151">Research has led Microsoft to be further concerned about CBC messages that are padded with ISO 10126-equivalent padding when the message has a well-known or predictable footer structure.</span></span> <span data-ttu-id="a1c46-152">例如，准备好的 W3C XML 加密语法和处理建议 (xmlenc，EncryptedXml 的) 的规则下的内容。</span><span class="sxs-lookup"><span data-stu-id="a1c46-152">For example, content prepared under the rules of the W3C XML Encryption Syntax and Processing Recommendation (xmlenc, EncryptedXml).</span></span> <span data-ttu-id="a1c46-153">W3C 指南以对消息进行签名，然后加密已视为适当时，Microsoft 现在建议始终进行加密并签名。</span><span class="sxs-lookup"><span data-stu-id="a1c46-153">While the W3C guidance to sign the message then encrypt was considered appropriate at the time, Microsoft now recommends always doing encrypt-then-sign.</span></span>

<span data-ttu-id="a1c46-154">因为没有任何非对称密钥和任意消息之间的内在的信任关系应用程序开发人员应始终为验证的非对称签名密钥，适用性的注意。</span><span class="sxs-lookup"><span data-stu-id="a1c46-154">Application developers should always be mindful of verifying the applicability of an asymmetric signature key, as there's no inherent trust relationship between an asymmetric key and an arbitrary message.</span></span>

## <a name="details"></a><span data-ttu-id="a1c46-155">详细信息</span><span class="sxs-lookup"><span data-stu-id="a1c46-155">Details</span></span>

<span data-ttu-id="a1c46-156">从历史上看，已被务必要加密和身份验证使用方式如 HMAC 或 RSA 签名的重要数据的一致。</span><span class="sxs-lookup"><span data-stu-id="a1c46-156">Historically, there has been consensus that it's important to both encrypt and authenticate important data, using means such as HMAC or RSA signatures.</span></span> <span data-ttu-id="a1c46-157">但是，已更少清晰指导如何进行序列化的加密和身份验证的操作。</span><span class="sxs-lookup"><span data-stu-id="a1c46-157">However, there has been less clear guidance as to how to sequence the encryption and authentication operations.</span></span> <span data-ttu-id="a1c46-158">由于此文章中详述的漏洞，Microsoft 的指导原则是现在始终使用"加密、 然后和签名的"模式。</span><span class="sxs-lookup"><span data-stu-id="a1c46-158">Due to the vulnerability detailed in this article, Microsoft's guidance is now to always use the "encrypt-then-sign" paradigm.</span></span> <span data-ttu-id="a1c46-159">也就是说，首先使用对称密钥加密数据，然后计算已加密文本 （加密的数据） 的 MAC 或非对称签名。</span><span class="sxs-lookup"><span data-stu-id="a1c46-159">That is, first encrypt data using a symmetric key, then compute a MAC or asymmetric signature over the ciphertext (encrypted data).</span></span> <span data-ttu-id="a1c46-160">时解密数据，则执行相反。</span><span class="sxs-lookup"><span data-stu-id="a1c46-160">When decrypting data, perform the reverse.</span></span> <span data-ttu-id="a1c46-161">首先，确认 MAC 或签名的已加密文本，然后将其解密。</span><span class="sxs-lookup"><span data-stu-id="a1c46-161">First, confirm the MAC or signature of the ciphertext, then decrypt it.</span></span>

<span data-ttu-id="a1c46-162">为"填充 oracle 攻击"已知存在超过 10 年的已知漏洞的类。</span><span class="sxs-lookup"><span data-stu-id="a1c46-162">A class of vulnerabilities known as "padding oracle attacks" have been known to exist for over 10 years.</span></span> <span data-ttu-id="a1c46-163">这些漏洞允许攻击者能够解密加密的对称块算法，如 AES 和 3DES，使用不超过 4096 个尝试每个数据块的数据。</span><span class="sxs-lookup"><span data-stu-id="a1c46-163">These vulnerabilities allow an attacker to decrypt data encrypted by symmetric block algorithms, such as AES and 3DES, using no more than 4096 attempts per block of data.</span></span> <span data-ttu-id="a1c46-164">这些漏洞使这一事实的块加密法使用最常用的末尾的可验证填充数据。</span><span class="sxs-lookup"><span data-stu-id="a1c46-164">These vulnerabilities make use of the fact that block ciphers are most frequently used with verifiable padding data at the end.</span></span> <span data-ttu-id="a1c46-165">已找到它，是否攻击者可以篡改已加密文本，并找出是否被篡改的末尾填充格式导致出现错误，则攻击者可以解密的数据。</span><span class="sxs-lookup"><span data-stu-id="a1c46-165">It was found that if an attacker can tamper with ciphertext and find out whether the tampering caused an error in the format of the padding at the end, the attacker can decrypt the data.</span></span>

<span data-ttu-id="a1c46-166">最初，实际的攻击已根据服务将返回不同的错误代码根据填充是否有效，如 ASP.NET 漏洞[MS10 070](https://technet.microsoft.com/library/security/ms10-070.aspx)。</span><span class="sxs-lookup"><span data-stu-id="a1c46-166">Initially, practical attacks were based on services that would return different error codes based on whether padding was valid, such as the ASP.NET vulnerability [MS10-070](https://technet.microsoft.com/library/security/ms10-070.aspx).</span></span> <span data-ttu-id="a1c46-167">但是，Microsoft 现在认为它是实际执行类似的攻击使用仅计时处理有效和无效的填充之间的差异。</span><span class="sxs-lookup"><span data-stu-id="a1c46-167">However, Microsoft now believes that it's practical to conduct similar attacks using only the differences in timing between processing valid and invalid padding.</span></span>

<span data-ttu-id="a1c46-168">提供的加密方案使用一个签名，而与给定长度的 （不考虑内容） 的数据固定的运行时执行签名验证，数据完整性可以验证而不发送到的任何信息攻击者通过[端通道](https://en.wikipedia.org/wiki/Side-channel_attack)。</span><span class="sxs-lookup"><span data-stu-id="a1c46-168">Provided that the encryption scheme employs a signature and that the signature verification is performed with a fixed runtime for a given length of data (irrespective of the contents), the data integrity can be verified without emitting any information to an attacker via a [side channel](https://en.wikipedia.org/wiki/Side-channel_attack).</span></span> <span data-ttu-id="a1c46-169">完整性检查会拒绝被篡改的任何消息，因为填充 oracle 威胁缓解。</span><span class="sxs-lookup"><span data-stu-id="a1c46-169">Since the integrity check rejects any tampered messages, the padding oracle threat is mitigated.</span></span>

## <a name="guidance"></a><span data-ttu-id="a1c46-170">指导</span><span class="sxs-lookup"><span data-stu-id="a1c46-170">Guidance</span></span>

<span data-ttu-id="a1c46-171">首先，这一 Microsoft 建议通过传输层安全 (TLS)，为安全套接字层 (SSL) 的继承者需要传输具有保密性的任何数据。</span><span class="sxs-lookup"><span data-stu-id="a1c46-171">First and foremost, Microsoft recommends that any data that has confidentiality needs be transmitted over Transport Layer Security (TLS), the successor to Secure Sockets Layer (SSL).</span></span>

<span data-ttu-id="a1c46-172">接下来，分析到应用程序：</span><span class="sxs-lookup"><span data-stu-id="a1c46-172">Next, analyze your application to:</span></span>

- <span data-ttu-id="a1c46-173">了解准确地说您正在执行哪些加密以及哪些加密由平台和正在使用的 Api。</span><span class="sxs-lookup"><span data-stu-id="a1c46-173">Understand precisely what encryption you're performing and what encryption is being provided by the platforms and APIs you're using.</span></span>
- <span data-ttu-id="a1c46-174">要确保每个使用情况，每个层的对称[块加密算法](https://en.wikipedia.org/wiki/Block_cipher#Notable_block_ciphers)，如 AES 和 3DES，CBC 模式下的将使用机密键控数据完整性检查 (的非对称签名的 HMAC，或若要更改到的密码模式[进行身份验证加密](https://en.wikipedia.org/wiki/Authenticated_encryption)(AE) 模式 GCM 或 CCM)。</span><span class="sxs-lookup"><span data-stu-id="a1c46-174">Be certain that each usage at each layer of a symmetric [block cipher algorithm](https://en.wikipedia.org/wiki/Block_cipher#Notable_block_ciphers), such as AES and 3DES, in CBC mode incorporate the use of a secret-keyed data integrity check (an asymmetric signature, an HMAC, or to change the cipher mode to an [authenticated encryption](https://en.wikipedia.org/wiki/Authenticated_encryption) (AE) mode such as GCM or CCM).</span></span>

<span data-ttu-id="a1c46-175">基于当前研究，因此通常认为，身份验证和加密步骤执行时独立于非 AE 模式加密的进行身份验证已加密文本 （加密、 然后和签名） 是最佳的常规选项。</span><span class="sxs-lookup"><span data-stu-id="a1c46-175">Based on the current research, it's generally believed that when the authentication and encryption steps are performed independently for non-AE modes of encryption, authenticating the ciphertext (encrypt-then-sign) is the best general option.</span></span> <span data-ttu-id="a1c46-176">但是，没有一刀切的正确解答加密技术，此正则化不是从专业的加密人员一样好定向的建议。</span><span class="sxs-lookup"><span data-stu-id="a1c46-176">However, there's no one-size-fits-all correct answer to cryptography and this generalization isn't as good as directed advice from a professional cryptographer.</span></span>

<span data-ttu-id="a1c46-177">无法更改其消息传送格式，但执行未经身份验证的 CBC 解密的应用程序被建议试图如合并的缓解措施：</span><span class="sxs-lookup"><span data-stu-id="a1c46-177">Applications that are unable to change their messaging format but perform unauthenticated CBC decryption are encouraged to try to incorporate mitigations such as:</span></span>

- <span data-ttu-id="a1c46-178">但不允许解密程序以进行验证或删除填充解密：</span><span class="sxs-lookup"><span data-stu-id="a1c46-178">Decrypt without allowing the decryptor to verify or remove padding:</span></span>
  - <span data-ttu-id="a1c46-179">已应用的任何填充仍需要删除或被忽略，在移动到你的应用程序的负担。</span><span class="sxs-lookup"><span data-stu-id="a1c46-179">Any padding that was applied still needs to be removed or ignored, you're moving the burden into your application.</span></span>
  - <span data-ttu-id="a1c46-180">好处是填充验证和删除可以合并到其他应用程序数据验证逻辑。</span><span class="sxs-lookup"><span data-stu-id="a1c46-180">The benefit is that the padding verification and removal can be incorporated into other application data verification logic.</span></span> <span data-ttu-id="a1c46-181">如果可以在常量时间内完成填充验证和数据验证，减少威胁。</span><span class="sxs-lookup"><span data-stu-id="a1c46-181">If the padding verification and data verification can be done in constant time, the threat is reduced.</span></span>
  - <span data-ttu-id="a1c46-182">因为填充的解释更改感知到的消息长度，也仍可能会从这种方法发出的计时信息。</span><span class="sxs-lookup"><span data-stu-id="a1c46-182">Since the interpretation of the padding changes the perceived message length, there may still be timing information emitted from this approach.</span></span>
- <span data-ttu-id="a1c46-183">将解密的填充模式更改为 ISO10126:</span><span class="sxs-lookup"><span data-stu-id="a1c46-183">Change the decryption padding mode to ISO10126:</span></span>
  - <span data-ttu-id="a1c46-184">ISO10126 解密填充状态是与 PKCS7 加密填充和 ANSIX923 加密填充兼容。</span><span class="sxs-lookup"><span data-stu-id="a1c46-184">ISO10126 decryption padding is compatible with both PKCS7 encryption padding and ANSIX923 encryption padding.</span></span>
  - <span data-ttu-id="a1c46-185">更改模式会填充 oracle 知识减少到 1 个字节而不是整个块。</span><span class="sxs-lookup"><span data-stu-id="a1c46-185">Changing the mode reduces the padding oracle knowledge to 1 byte instead of the entire block.</span></span> <span data-ttu-id="a1c46-186">但是，如果内容具有已知的页脚中，将结束 XML 元素，如可以继续相关的攻击来攻击消息的剩余部分。</span><span class="sxs-lookup"><span data-stu-id="a1c46-186">However, if the content has a well-known footer, such as a closing XML element, related attacks can continue to attack the rest of the message.</span></span>
  - <span data-ttu-id="a1c46-187">这还不会阻止在攻击者可以对相同的纯文本进行加密具有不同的消息的偏移量的多个时间强制转换的情况下的纯文本恢复。</span><span class="sxs-lookup"><span data-stu-id="a1c46-187">This also doesn't prevent plaintext recovery in situations where the attacker can coerce the same plaintext to be encrypted multiple times with a different message offset.</span></span>
- <span data-ttu-id="a1c46-188">入口解密调用消除计时信号的评估：</span><span class="sxs-lookup"><span data-stu-id="a1c46-188">Gate the evaluation of a decryption call to dampen the timing signal:</span></span>
  - <span data-ttu-id="a1c46-189">计算的保留时间必须至少超出最大，解密操作将需要为包含填充任何数据段的时间量。</span><span class="sxs-lookup"><span data-stu-id="a1c46-189">The computation of hold time must have a minimum in excess of the maximum amount of time the decryption operation would take for any data segment that contains padding.</span></span>
  - <span data-ttu-id="a1c46-190">应根据中的指导完成时间计算[获取高分辨率时间戳](https://msdn.microsoft.com/library/windows/desktop/dn55340.aspx)，不能通过使用<xref:System.Environment.TickCount?displayProperty=nameWithType>（取决于前的 over/溢出） 或减法 （取决于 NTP 调整的两个系统时间戳错误）。</span><span class="sxs-lookup"><span data-stu-id="a1c46-190">Time computations should be done according to the guidance in [Acquiring high-resolution time stamps](https://msdn.microsoft.com/library/windows/desktop/dn55340.aspx), not by using <xref:System.Environment.TickCount?displayProperty=nameWithType> (subject to roll-over/overflow) or subtracting two system timestamps (subject to NTP adjustment errors).</span></span>
  - <span data-ttu-id="a1c46-191">时间计算必须包括解密操作包括中的所有潜在异常管理或 c + + 应用程序，而不仅仅是填充到末尾。</span><span class="sxs-lookup"><span data-stu-id="a1c46-191">Time computations must be inclusive of the decryption operation including all potential exceptions in managed or C++ applications, not just padded onto the end.</span></span>
  - <span data-ttu-id="a1c46-192">如果尚未确定成功或失败，计时入口将需要它过期时返回失败。</span><span class="sxs-lookup"><span data-stu-id="a1c46-192">If success or failure has been determined yet, the timing gate needs to return failure when it expires.</span></span>
- <span data-ttu-id="a1c46-193">正在执行未经身份验证的解密的服务应具有在来检测大量"无效"消息都监视。</span><span class="sxs-lookup"><span data-stu-id="a1c46-193">Services that are performing unauthenticated decryption should have monitoring in place to detect that a flood of "invalid" messages has come through.</span></span>
  - <span data-ttu-id="a1c46-194">请记住此信号携带的假正值 （以合法方式损坏的数据） 和假负 （分散通过足够长的时间来躲避检测攻击）。</span><span class="sxs-lookup"><span data-stu-id="a1c46-194">Bear in mind that this signal carries both false positives (legitimately corrupted data) and false negatives (spreading out the attack over a sufficiently long time to evade detection).</span></span>

## <a name="finding-vulnerable-code---native-applications"></a><span data-ttu-id="a1c46-195">查找易受攻击代码的本机应用程序</span><span class="sxs-lookup"><span data-stu-id="a1c46-195">Finding vulnerable code - native applications</span></span>

<span data-ttu-id="a1c46-196">有关生成针对 Windows 加密程序： Next Generation (CNG) 库：</span><span class="sxs-lookup"><span data-stu-id="a1c46-196">For programs built against the Windows Cryptography: Next Generation (CNG) library:</span></span>

- <span data-ttu-id="a1c46-197">解密调用是对[BCryptDecrypt](/windows/desktop/api/bcrypt/nf-bcrypt-bcryptdecrypt)，并指定`BCRYPT_BLOCK_PADDING`标志。</span><span class="sxs-lookup"><span data-stu-id="a1c46-197">The decryption call is to [BCryptDecrypt](/windows/desktop/api/bcrypt/nf-bcrypt-bcryptdecrypt), specifying the `BCRYPT_BLOCK_PADDING` flag.</span></span>
- <span data-ttu-id="a1c46-198">通过调用已初始化的密钥句柄[BCryptSetProperty](/windows/desktop/api/bcrypt/nf-bcrypt-bcryptsetproperty)与[BCRYPT_CHAINING_MODE](https://msdn.microsoft.com/library/windows/desktop/aa376211.aspx#BCRYPT_CHAINING_MODE)设置为`BCRYPT_CHAIN_MODE_CBC`。</span><span class="sxs-lookup"><span data-stu-id="a1c46-198">The key handle has been initialized by calling [BCryptSetProperty](/windows/desktop/api/bcrypt/nf-bcrypt-bcryptsetproperty) with [BCRYPT_CHAINING_MODE](https://msdn.microsoft.com/library/windows/desktop/aa376211.aspx#BCRYPT_CHAINING_MODE) set to `BCRYPT_CHAIN_MODE_CBC`.</span></span>
  - <span data-ttu-id="a1c46-199">由于`BCRYPT_CHAIN_MODE_CBC`是默认情况下，受影响的代码可能未分配任何值`BCRYPT_CHAINING_MODE`。</span><span class="sxs-lookup"><span data-stu-id="a1c46-199">Since `BCRYPT_CHAIN_MODE_CBC` is the default, affected code may not have assigned any value for `BCRYPT_CHAINING_MODE`.</span></span>

<span data-ttu-id="a1c46-200">针对较旧的 Windows 加密 API 生成的程序：</span><span class="sxs-lookup"><span data-stu-id="a1c46-200">For programs built against the older Windows Cryptographic API:</span></span>

- <span data-ttu-id="a1c46-201">解密调用是对[CryptDecrypt](/windows/desktop/api/wincrypt/nf-wincrypt-cryptdecrypt)与`Final=TRUE`。</span><span class="sxs-lookup"><span data-stu-id="a1c46-201">The decryption call is to [CryptDecrypt](/windows/desktop/api/wincrypt/nf-wincrypt-cryptdecrypt) with `Final=TRUE`.</span></span>
- <span data-ttu-id="a1c46-202">通过调用已初始化的密钥句柄[CryptSetKeyParam](/windows/desktop/api/wincrypt/nf-wincrypt-cryptsetkeyparam)与[KP_MODE](https://msdn.microsoft.com/library/windows/desktop/aa379949.aspx#KP_MODE)设置为`CRYPT_MODE_CBC`。</span><span class="sxs-lookup"><span data-stu-id="a1c46-202">The key handle has been initialized by calling [CryptSetKeyParam](/windows/desktop/api/wincrypt/nf-wincrypt-cryptsetkeyparam) with [KP_MODE](https://msdn.microsoft.com/library/windows/desktop/aa379949.aspx#KP_MODE) set to `CRYPT_MODE_CBC`.</span></span>
  - <span data-ttu-id="a1c46-203">由于`CRYPT_MODE_CBC`是默认情况下，受影响的代码可能未分配任何值`KP_MODE`。</span><span class="sxs-lookup"><span data-stu-id="a1c46-203">Since `CRYPT_MODE_CBC` is the default, affected code may not have assigned any value for `KP_MODE`.</span></span>

## <a name="finding-vulnerable-code---managed-applications"></a><span data-ttu-id="a1c46-204">查找易受攻击代码的托管应用程序</span><span class="sxs-lookup"><span data-stu-id="a1c46-204">Finding vulnerable code - managed applications</span></span>

- <span data-ttu-id="a1c46-205">解密调用是对<xref:System.Security.Cryptography.SymmetricAlgorithm.CreateDecryptor>或<xref:System.Security.Cryptography.SymmetricAlgorithm.CreateDecryptor(System.Byte[],System.Byte[])>上的方法<xref:System.Security.Cryptography.SymmetricAlgorithm?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="a1c46-205">The decryption call is to the <xref:System.Security.Cryptography.SymmetricAlgorithm.CreateDecryptor> or <xref:System.Security.Cryptography.SymmetricAlgorithm.CreateDecryptor(System.Byte[],System.Byte[])> methods on <xref:System.Security.Cryptography.SymmetricAlgorithm?displayProperty=nameWithType>.</span></span>
  - <span data-ttu-id="a1c46-206">这包括在.NET 中，以下的派生的类型，但可能还包括第三方类型：</span><span class="sxs-lookup"><span data-stu-id="a1c46-206">This includes the following derived types within the .NET, but may also include third-party types:</span></span>
    - <xref:System.Security.Cryptography.Aes>
    - <xref:System.Security.Cryptography.AesCng>
    - <xref:System.Security.Cryptography.AesCryptoServiceProvider>
    - <xref:System.Security.Cryptography.AesManaged>
    - <xref:System.Security.Cryptography.DES>
    - <xref:System.Security.Cryptography.DESCryptoServiceProvider>
    - <xref:System.Security.Cryptography.RC2>
    - <xref:System.Security.Cryptography.RC2CryptoServiceProvider>
    - <xref:System.Security.Cryptography.Rijndael>
    - <xref:System.Security.Cryptography.RijndaelManaged>
    - <xref:System.Security.Cryptography.TripleDES>
    - <xref:System.Security.Cryptography.TripleDESCng>
    - <xref:System.Security.Cryptography.TripleDESCryptoServiceProvider>
- <span data-ttu-id="a1c46-207"><xref:System.Security.Cryptography.SymmetricAlgorithm.Padding?displayProperty=nameWithType>属性设置为<xref:System.Security.Cryptography.PaddingMode.PKCS7?displayProperty=nameWithType>， <xref:System.Security.Cryptography.PaddingMode.ANSIX923?displayProperty=nameWithType>，或<xref:System.Security.Cryptography.PaddingMode.ISO10126?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="a1c46-207">The <xref:System.Security.Cryptography.SymmetricAlgorithm.Padding?displayProperty=nameWithType> property was set to <xref:System.Security.Cryptography.PaddingMode.PKCS7?displayProperty=nameWithType>, <xref:System.Security.Cryptography.PaddingMode.ANSIX923?displayProperty=nameWithType>, or <xref:System.Security.Cryptography.PaddingMode.ISO10126?displayProperty=nameWithType>.</span></span>
  - <span data-ttu-id="a1c46-208">由于<xref:System.Security.Cryptography.PaddingMode.PKCS7?displayProperty=nameWithType>是默认情况下，受影响的代码可能永远不会分配<xref:System.Security.Cryptography.SymmetricAlgorithm.Padding?displayProperty=nameWithType>属性。</span><span class="sxs-lookup"><span data-stu-id="a1c46-208">Since <xref:System.Security.Cryptography.PaddingMode.PKCS7?displayProperty=nameWithType> is the default, affected code may never have assigned the <xref:System.Security.Cryptography.SymmetricAlgorithm.Padding?displayProperty=nameWithType> property.</span></span>
- <span data-ttu-id="a1c46-209"><xref:System.Security.Cryptography.SymmetricAlgorithm.Mode?displayProperty=nameWithType>属性被设置为 <xref:System.Security.Cryptography.CipherMode.CBC?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="a1c46-209">The <xref:System.Security.Cryptography.SymmetricAlgorithm.Mode?displayProperty=nameWithType> property was set to <xref:System.Security.Cryptography.CipherMode.CBC?displayProperty=nameWithType></span></span>
  - <span data-ttu-id="a1c46-210">由于<xref:System.Security.Cryptography.CipherMode.CBC?displayProperty=nameWithType>是默认情况下，受影响的代码可能永远不会分配<xref:System.Security.Cryptography.SymmetricAlgorithm.Mode?displayProperty=nameWithType>属性。</span><span class="sxs-lookup"><span data-stu-id="a1c46-210">Since <xref:System.Security.Cryptography.CipherMode.CBC?displayProperty=nameWithType> is the default, affected code may never have assigned the <xref:System.Security.Cryptography.SymmetricAlgorithm.Mode?displayProperty=nameWithType> property.</span></span>

## <a name="finding-vulnerable-code---cryptographic-message-syntax"></a><span data-ttu-id="a1c46-211">查找易受攻击代码的加密消息语法</span><span class="sxs-lookup"><span data-stu-id="a1c46-211">Finding vulnerable code - cryptographic message syntax</span></span>

<span data-ttu-id="a1c46-212">其加密的内容使用 CBC 模式的 AES （2.16.840.1.101.3.4.1.2，2.16.840.1.101.3.4.1.22，2.16.840.1.101.3.4.1.42）、 DES (1.3.14.3.2.7)、 3DES 的未经身份验证的 CMS EnvelopedData 消息 (1.2.840.113549.3.7) 或 RC2 (1.2.840.113549.3.2) 是易受攻击，以及为消息使用 CBC 模式下的任何其他块密码算法。</span><span class="sxs-lookup"><span data-stu-id="a1c46-212">An unauthenticated CMS EnvelopedData message whose encrypted content uses the CBC mode of AES (2.16.840.1.101.3.4.1.2, 2.16.840.1.101.3.4.1.22, 2.16.840.1.101.3.4.1.42), DES (1.3.14.3.2.7), 3DES (1.2.840.113549.3.7) or RC2 (1.2.840.113549.3.2) is vulnerable, as well as messages using any other block cipher algorithms in CBC mode.</span></span>

<span data-ttu-id="a1c46-213">虽然流加密法并不容易受到此特定漏洞，Microsoft 建议始终通过检查 ContentEncryptionAlgorithm 值身份验证数据。</span><span class="sxs-lookup"><span data-stu-id="a1c46-213">While stream ciphers aren't susceptible to this particular vulnerability, Microsoft recommends always authenticating the data over inspecting the ContentEncryptionAlgorithm value.</span></span>

<span data-ttu-id="a1c46-214">对于托管应用程序，blob 可以是 CMS EnvelopedData 检测到传递给任何值<xref:System.Security.Cryptography.Pkcs.EnvelopedCms.Decode(System.Byte[])?displayProperty=fullName>。</span><span class="sxs-lookup"><span data-stu-id="a1c46-214">For managed applications, a CMS EnvelopedData blob can be detected as any value that is passed to <xref:System.Security.Cryptography.Pkcs.EnvelopedCms.Decode(System.Byte[])?displayProperty=fullName>.</span></span>

<span data-ttu-id="a1c46-215">对于本机应用程序，CMS EnvelopedData blob 可以检测到的句柄 CMS 通过提供的任何值作为[CryptMsgUpdate](/windows/desktop/api/wincrypt/nf-wincrypt-cryptmsgupdate)其从而[CMSG_TYPE_PARAM](/windows/desktop/api/wincrypt/nf-wincrypt-cryptmsggetparam)是`CMSG_ENVELOPED`和/或 CMS 句柄是更高版本发送`CMSG_CTRL_DECRYPT`通过指令[CryptMsgControl](/windows/desktop/api/wincrypt/nf-wincrypt-cryptmsgcontrol)。</span><span class="sxs-lookup"><span data-stu-id="a1c46-215">For native applications, a CMS EnvelopedData blob can be detected as any value provided to a CMS handle via [CryptMsgUpdate](/windows/desktop/api/wincrypt/nf-wincrypt-cryptmsgupdate) whose resulting [CMSG_TYPE_PARAM](/windows/desktop/api/wincrypt/nf-wincrypt-cryptmsggetparam) is `CMSG_ENVELOPED` and/or the CMS handle is later sent a `CMSG_CTRL_DECRYPT` instruction via [CryptMsgControl](/windows/desktop/api/wincrypt/nf-wincrypt-cryptmsgcontrol).</span></span>

## <a name="vulnerable-code-example---managed"></a><span data-ttu-id="a1c46-216">易受攻击的代码示例-管理</span><span class="sxs-lookup"><span data-stu-id="a1c46-216">Vulnerable code example - managed</span></span>

<span data-ttu-id="a1c46-217">此方法读取 cookie，并对其进行解密，并显示任何数据完整性检查。</span><span class="sxs-lookup"><span data-stu-id="a1c46-217">This method reads a cookie and decrypts it and no data integrity check is visible.</span></span> <span data-ttu-id="a1c46-218">因此，通过此方法读取 cookie 的内容可以由用户获得，或通过任何攻击者获得加密的 cookie 值受到攻击。</span><span class="sxs-lookup"><span data-stu-id="a1c46-218">Therefore, the contents of a cookie that is read by this method can be attacked by the user who received it, or by any attacker who has obtained the encrypted cookie value.</span></span>

```csharp
private byte[] DecryptCookie(string cookieName)
{
    HttpCookie cookie = Request.Cookies[cookieName];

    if (cookie == null)
    {
        return null;
    }

    using (ICryptoTransform decryptor = _aes.CreateDecryptor())
    using (MemoryStream memoryStream = new MemoryStream())
    using (CryptoStream cryptoStream =
        new CryptoStream(memoryStream, decryptor, CryptoStreamMode.Write))
    {
        byte[] readCookie = Convert.FromBase64String(cookie.Value);
        cryptoStream.Write(readCookie, 0, readCookie.Length);
        cryptoStream.FlushFinalBlock();
        return memoryStream.ToArray();
    }
}
```

## <a name="example-code-following-recommended-practices---managed"></a><span data-ttu-id="a1c46-219">以下示例代码建议的做法-管理</span><span class="sxs-lookup"><span data-stu-id="a1c46-219">Example code following recommended practices - managed</span></span>

<span data-ttu-id="a1c46-220">下面的示例代码使用非标准的消息的格式</span><span class="sxs-lookup"><span data-stu-id="a1c46-220">The following sample code uses a non-standard message format of</span></span>

`cipher_algorithm_id || hmac_algorithm_id || hmac_tag || iv || ciphertext`

<span data-ttu-id="a1c46-221">其中`cipher_algorithm_id`和`hmac_algorithm_id`算法标识符是这些算法的应用程序本地 （非标准） 表示。</span><span class="sxs-lookup"><span data-stu-id="a1c46-221">where the `cipher_algorithm_id` and `hmac_algorithm_id` algorithm identifiers are application-local (non-standard) representations of those algorithms.</span></span> <span data-ttu-id="a1c46-222">这些标识符可能意义而不是您现有的消息传递协议的其他部分中为裸机串联字节流。</span><span class="sxs-lookup"><span data-stu-id="a1c46-222">These identifiers may make sense in other parts of your existing messaging protocol instead of as a bare concatenated bytestream.</span></span>

<span data-ttu-id="a1c46-223">此示例还使用单个主密钥来派生的加密密钥和 HMAC 密钥。</span><span class="sxs-lookup"><span data-stu-id="a1c46-223">This example also uses a single master key to derive both an encryption key and an HMAC key.</span></span> <span data-ttu-id="a1c46-224">这是用于启用一个单向键控应用程序到双键控应用程序，并建议保存为不同的值的两个密钥提供了为方便起见。</span><span class="sxs-lookup"><span data-stu-id="a1c46-224">This is provided both as a convenience for turning a singly-keyed application into a dual-keyed application, and to encourage keeping the two keys as different values.</span></span> <span data-ttu-id="a1c46-225">它进一步确保 HMAC 密钥和加密密钥无法获取不同步。</span><span class="sxs-lookup"><span data-stu-id="a1c46-225">It further guarantees that the HMAC key and encryption key can't get out of synchronization.</span></span>

<span data-ttu-id="a1c46-226">此示例不接受<xref:System.IO.Stream>实现加密或解密。</span><span class="sxs-lookup"><span data-stu-id="a1c46-226">This sample doesn't accept a <xref:System.IO.Stream> for either encryption or decryption.</span></span> <span data-ttu-id="a1c46-227">当前的数据格式进行单步加密困难因为`hmac_tag`值之前已加密文本。</span><span class="sxs-lookup"><span data-stu-id="a1c46-227">The current data format makes one-pass encrypt difficult because the `hmac_tag` value precedes the ciphertext.</span></span> <span data-ttu-id="a1c46-228">但是，因为它将保持分析器更简单的开头的所有固定大小元素选择这种格式。</span><span class="sxs-lookup"><span data-stu-id="a1c46-228">However, this format was chosen because it keeps all of the fixed-size elements at the beginning to keep the parser simpler.</span></span> <span data-ttu-id="a1c46-229">使用这种数据格式，一遍解密是可能的但实现器警告调用 GetHashAndReset 并调用 TransformFinalBlock 之前验证结果。</span><span class="sxs-lookup"><span data-stu-id="a1c46-229">With this data format, one-pass decrypt is possible, though an implementer is cautioned to call GetHashAndReset and verify the result before calling TransformFinalBlock.</span></span> <span data-ttu-id="a1c46-230">如果流式处理加密很重要，则可能需要不同的 AE 模式。</span><span class="sxs-lookup"><span data-stu-id="a1c46-230">If streaming encryption is important, then a different AE mode may be required.</span></span>

```csharp
// ==++==
//
//   Copyright (c) Microsoft Corporation.  All rights reserved.
//
//   Shared under the terms of the Microsoft Public License,
//   https://opensource.org/licenses/MS-PL
//
// ==--==

using System;
using System.Diagnostics;
using System.IO;
using System.Runtime.CompilerServices;
using System.Security.Cryptography;

namespace Microsoft.Examples.Cryptography
{
    public enum AeCipher : byte
    {
        Unknown,
        Aes256CbcPkcs7,
    }

    public enum AeMac : byte
    {
        Unknown,
        HMACSHA256,
        HMACSHA384,
    }

    /// <summary>
    /// Provides extension methods to make HashAlgorithm look like .NET Core's
    /// IncrementalHash
    /// </summary>
    internal static class IncrementalHashExtensions
    {
        public static void AppendData(this HashAlgorithm hash, byte[] data)
        {
            hash.TransformBlock(data, 0, data.Length, null, 0);
        }

        public static void AppendData(
            this HashAlgorithm hash,
            byte[] data,
            int offset,
            int length)
        {
            hash.TransformBlock(data, offset, length, null, 0);
        }

        public static byte[] GetHashAndReset(this HashAlgorithm hash)
        {
            hash.TransformFinalBlock(Array.Empty<byte>(), 0, 0);
            return hash.Hash;
        }
    }

    public static partial class AuthenticatedEncryption
    {
        /// <summary>
        /// Use <paramref name="masterKey"/> to derive two keys (one cipher, one HMAC)
        /// to provide authenticated encryption for <paramref name="message"/>.
        /// </summary>
        /// <param name="masterKey">The master key from which other keys derive.</param>
        /// <param name="message">The message to encrypt</param>
        /// <returns>
        /// A concatenation of
        /// [cipher algorithm+chainmode+padding][mac algorithm][authtag][IV][ciphertext],
        /// suitable to be passed to <see cref="Decrypt"/>.
        /// </returns>
        /// <remarks>
        /// <paramref name="masterKey"/> should be a 128-bit (or bigger) value generated
        /// by a secure random number generator, such as the one returned from
        /// <see cref="RandomNumberGenerator.Create()"/>.
        /// This implementation chooses to block deficient inputs by length, but does not
        /// make any attempt at discerning the randomness of the key.
        ///
        /// If the master key is being input by a prompt (like a password/passphrase)
        /// then it should be properly turned into keying material via a Key Derivation
        /// Function like PBKDF2, represented by Rfc2898DeriveBytes. A 'password' should
        /// never be simply turned to bytes via an Encoding class and used as a key.
        /// </remarks>
        public static byte[] Encrypt(byte[] masterKey, byte[] message)
        {
            if (masterKey == null)
                throw new ArgumentNullException(nameof(masterKey));
            if (masterKey.Length < 16)
                throw new ArgumentOutOfRangeException(
                    nameof(masterKey),
                    "Master Key must be at least 128 bits (16 bytes)");
            if (message == null)
                throw new ArgumentNullException(nameof(message));

            // First, choose an encryption scheme.
            AeCipher aeCipher = AeCipher.Aes256CbcPkcs7;

            // Second, choose an authentication (message integrity) scheme.
            //
            // In this example we use the master key length to change from HMACSHA256 to
            // HMACSHA384, but that is completely arbitrary. This mostly represents a
            // "cryptographic needs change over time" scenario.
            AeMac aeMac = masterKey.Length < 48 ? AeMac.HMACSHA256 : AeMac.HMACSHA384;

            // It's good to be able to identify what choices were made when a message was
            // encrypted, so that the message can later be decrypted. This allows for
            // future versions to add support for new encryption schemes, but still be
            // able to read old data. A practice known as "cryptographic agility".
            //
            // This is similar in practice to PKCS#7 messaging, but this uses a
            // private-scoped byte rather than a public-scoped Object IDentifier (OID).
            // Please note that the scheme in this example adheres to no particular
            // standard, and is unlikely to survive to a more complete implementation in
            // the .NET Framework.
            //
            // You may be well-served by prepending a version number byte to this
            // message, but may want to avoid the value 0x30 (the leading byte value for
            // DER-encoded structures such as X.509 certificates and PKCS#7 messages).
            byte[] algorithmChoices = { (byte)aeCipher, (byte)aeMac };
            byte[] iv;
            byte[] cipherText;
            byte[] tag;

            // Using our algorithm choices, open an HMAC (as an authentication tag
            // generator) and a SymmetricAlgorithm which use different keys each derived
            // from the same master key.
            //
            // A custom implementation may very well have distinctly managed secret keys
            // for the MAC and cipher, this example merely demonstrates the master to
            // derived key methodology to encourage key separation from the MAC and
            // cipher keys.
            using (HMAC tagGenerator = GetMac(aeMac, masterKey))
            {
                using (SymmetricAlgorithm cipher = GetCipher(aeCipher, masterKey))
                using (ICryptoTransform encryptor = cipher.CreateEncryptor())
                {
                    // Since no IV was provided, a random one has been generated
                    // during the call to CreateEncryptor.
                    //
                    // But note that it only does the auto-generation once. If the cipher
                    // object were used again, a call to GenerateIV would have been
                    // required.
                    iv = cipher.IV;

                    cipherText = Transform(encryptor, message, 0, message.Length);
                }

                // The IV and ciphertest both need to be included in the MAC to prevent
                // tampering.
                //
                // By including the algorithm identifiers, we have technically moved from
                // simple Authenticated Encryption (AE) to Authenticated Encryption with
                // Additional Data (AEAD). By including the algorithm identifiers in the
                // MAC, it becomes harder for an attacker to change them as an attempt to
                // perform a downgrade attack.
                //
                // If you've added a data format version field, it can also be included
                // in the MAC to further inhibit an attacker's options for confusing the
                // data processor into believing the tampered message is valid.
                tagGenerator.AppendData(algorithmChoices);
                tagGenerator.AppendData(iv);
                tagGenerator.AppendData(cipherText);
                tag = tagGenerator.GetHashAndReset();
            }

            // Build the final result as the concatenation of everything except the keys.
            int totalLength =
                algorithmChoices.Length +
                tag.Length +
                iv.Length +
                cipherText.Length;

            byte[] output = new byte[totalLength];
            int outputOffset = 0;

            Append(algorithmChoices, output, ref outputOffset);
            Append(tag, output, ref outputOffset);
            Append(iv, output, ref outputOffset);
            Append(cipherText, output, ref outputOffset);

            Debug.Assert(outputOffset == output.Length);
            return output;
        }

        /// <summary>
        /// Reads a message produced by <see cref="Encrypt"/> after verifying it hasn't
        /// been tampered with.
        /// </summary>
        /// <param name="masterKey">The master key from which other keys derive.</param>
        /// <param name="cipherText">
        /// The output of <see cref="Encrypt"/>: a concatenation of a cipher ID, mac ID,
        /// authTag, IV, and cipherText.
        /// </param>
        /// <returns>The decrypted content.</returns>
        /// <exception cref="ArgumentNullException">
        /// <paramref name="masterKey"/> is <c>null</c>.
        /// </exception>
        /// <exception cref="ArgumentNullException">
        /// <paramref name="cipherText"/> is <c>null</c>.
        /// </exception>
        /// <exception cref="CryptographicException">
        /// <paramref name="cipherText"/> identifies unknown algorithms, is not long
        /// enough, fails a data integrity check, or fails to decrypt.
        /// </exception>
        /// <remarks>
        /// <paramref name="masterKey"/> should be a 128-bit (or larger) value
        /// generated by a secure random number generator, such as the one returned from
        /// <see cref="RandomNumberGenerator.Create()"/>. This implementation chooses to
        /// block deficient inputs by length, but doesn't make any attempt at
        /// discerning the randomness of the key.
        ///
        /// If the master key is being input by a prompt (like a password/passphrase),
        /// then it should be properly turned into keying material via a Key Derivation
        /// Function like PBKDF2, represented by Rfc2898DeriveBytes. A 'password' should
        /// never be simply turned to bytes via an Encoding class and used as a key.
        /// </remarks>
        public static byte[] Decrypt(byte[] masterKey, byte[] cipherText)
        {
            // This example continues the .NET practice of throwing exceptions for
            // failures. If you consider message tampering to be normal (and thus
            // "not exceptional") behavior, you may like the signature
            // bool Decrypt(byte[] messageKey, byte[] cipherText, out byte[] message)
            // better.
            if (masterKey == null)
                throw new ArgumentNullException(nameof(masterKey));
            if (masterKey.Length < 16)
                throw new ArgumentOutOfRangeException(
                    nameof(masterKey),
                    "Master Key must be at least 128 bits (16 bytes)");
            if (cipherText == null)
                throw new ArgumentNullException(nameof(cipherText));

            // The format of this message is assumed to be public, so there's no harm in
            // saying ahead of time that the message makes no sense.
            if (cipherText.Length < 2)
            {
                throw new CryptographicException();
            }

            // Use the message algorithm headers to determine what cipher algorithm and
            // MAC algorithm are going to be used. Since the same Key Derivation
            // Functions (KDFs) are being used in Decrypt as Encrypt, the keys are also
            // the same.
            AeCipher aeCipher = (AeCipher)cipherText[0];
            AeMac aeMac = (AeMac)cipherText[1];

            using (SymmetricAlgorithm cipher = GetCipher(aeCipher, masterKey))
            using (HMAC tagGenerator = GetMac(aeMac, masterKey))
            {
                int blockSizeInBytes = cipher.BlockSize / 8;
                int tagSizeInBytes = tagGenerator.HashSize / 8;
                int headerSizeInBytes = 2;
                int tagOffset = headerSizeInBytes;
                int ivOffset = tagOffset + tagSizeInBytes;
                int cipherTextOffset = ivOffset + blockSizeInBytes;
                int cipherTextLength = cipherText.Length - cipherTextOffset;
                int minLen = cipherTextOffset + blockSizeInBytes;

                // Again, the minimum length is still assumed to be public knowledge,
                // nothing has leaked out yet. The minimum length couldn't just be calculated
                // without reading the header.
                if (cipherText.Length < minLen)
                {
                    throw new CryptographicException();
                }

                // It's very important that the MAC be calculated and verified before
                // proceeding to decrypt the ciphertext, as this prevents any sort of
                // information leaking out to an attacker.
                //
                // Don't include the tag in the calculation, though.

                // First, everything before the tag (the cipher and MAC algorithm ids)
                tagGenerator.AppendData(cipherText, 0, tagOffset);

                // Skip the data before the tag and the tag, then read everything that
                // remains.
                tagGenerator.AppendData(
                    cipherText,
                    tagOffset + tagSizeInBytes,
                    cipherText.Length - tagSizeInBytes - tagOffset);

                byte[] generatedTag = tagGenerator.GetHashAndReset();

                // The time it took to get to this point has so far been a function only
                // of the length of the data, or of non-encrypted values (e.g. it could
                // take longer to prepare the *key* for the HMACSHA384 MAC than the
                // HMACSHA256 MAC, but the algorithm choice wasn't a secret).
                //
                // If the verification of the authentication tag aborts as soon as a
                // difference is found in the byte arrays then your program may be
                // acting as a timing oracle which helps an attacker to brute-force the
                // right answer for the MAC. So, it's very important that every possible
                // "no" (2^256-1 of them for HMACSHA256) be evaluated in as close to the
                // same amount of time as possible. For this, we call CryptographicEquals
                if (!CryptographicEquals(
                    generatedTag,
                    0,
                    cipherText,
                    tagOffset,
                    tagSizeInBytes))
                {
                    // Assuming every tampered message (of the same length) took the same
                    // amount of time to process, we can now safely say
                    // "this data makes no sense" without giving anything away.
                    throw new CryptographicException();
                }

                // Restore the IV into the symmetricAlgorithm instance.
                byte[] iv = new byte[blockSizeInBytes];
                Buffer.BlockCopy(cipherText, ivOffset, iv, 0, iv.Length);
                cipher.IV = iv;

                using (ICryptoTransform decryptor = cipher.CreateDecryptor())
                {
                    return Transform(
                        decryptor,
                        cipherText,
                        cipherTextOffset,
                        cipherTextLength);
                }
            }
        }

        private static byte[] Transform(
            ICryptoTransform transform,
            byte[] input,
            int inputOffset,
            int inputLength)
        {
            // Many of the implementations of ICryptoTransform report true for
            // CanTransformMultipleBlocks, and when the entire message is available in
            // one shot this saves on the allocation of the CryptoStream and the
            // intermediate structures it needs to properly chunk the message into blocks
            // (since the underlying stream won't always return the number of bytes
            // needed).
            if (transform.CanTransformMultipleBlocks)
            {
                return transform.TransformFinalBlock(input, inputOffset, inputLength);
            }

            // If our transform couldn't do multiple blocks at once, let CryptoStream
            // handle the chunking.
            using (MemoryStream messageStream = new MemoryStream())
            using (CryptoStream cryptoStream =
                new CryptoStream(messageStream, transform, CryptoStreamMode.Write))
            {
                cryptoStream.Write(input, inputOffset, inputLength);
                cryptoStream.FlushFinalBlock();
                return messageStream.ToArray();
            }
        }

        /// <summary>
        /// Open a properly configured <see cref="SymmetricAlgorithm"/> conforming to the
        /// scheme identified by <paramref name="aeCipher"/>.
        /// </summary>
        /// <param name="aeCipher">The cipher mode to open.</param>
        /// <param name="masterKey">The master key from which other keys derive.</param>
        /// <returns>
        /// A SymmetricAlgorithm object with the right key, cipher mode, and padding
        /// mode; or <c>null</c> on unknown algorithms.
        /// </returns>
        private static SymmetricAlgorithm GetCipher(AeCipher aeCipher, byte[] masterKey)
        {
            SymmetricAlgorithm symmetricAlgorithm;

            switch (aeCipher)
            {
                case AeCipher.Aes256CbcPkcs7:
                    symmetricAlgorithm = Aes.Create();
                    // While 256-bit, CBC, and PKCS7 are all the default values for these
                    // properties, being explicit helps comprehension more than it hurts
                    // performance.
                    symmetricAlgorithm.KeySize = 256;
                    symmetricAlgorithm.Mode = CipherMode.CBC;
                    symmetricAlgorithm.Padding = PaddingMode.PKCS7;
                    break;
                default:
                    // An algorithm we don't understand
                    throw new CryptographicException();
            }

            // Instead of using the master key directly, derive a key for our chosen
            // HMAC algorithm based upon the master key.
            //
            // Since none of the symmetric encryption algorithms currently in .NET
            // support key sizes greater than 256-bit, we can use HMACSHA256 with
            // NIST SP 800-108 5.1 (Counter Mode KDF) to derive a value that is
            // no smaller than the key size, then Array.Resize to trim it down as
            // needed.

            using (HMAC hmac = new HMACSHA256(masterKey))
            {
                // i=1, Label=ASCII(cipher)
                byte[] cipherKey = hmac.ComputeHash(
                    new byte[] { 1, 99, 105, 112, 104, 101, 114 });

                // Resize the array to the desired keysize. KeySize is in bits,
                // and Array.Resize wants the length in bytes.
                Array.Resize(ref cipherKey, symmetricAlgorithm.KeySize / 8);

                symmetricAlgorithm.Key = cipherKey;
            }

            return symmetricAlgorithm;
        }

        /// <summary>
        /// Open a properly configured <see cref="HMAC"/> conforming to the scheme
        /// identified by <paramref name="aeMac"/>.
        /// </summary>
        /// <param name="aeMac">The message authentication mode to open.</param>
        /// <param name="masterKey">The master key from which other keys derive.</param>
        /// <returns>
        /// An HMAC object with the proper key, or <c>null</c> on unknown algorithms.
        /// </returns>
        private static HMAC GetMac(AeMac aeMac, byte[] masterKey)
        {
            HMAC hmac;

            switch (aeMac)
            {
                case AeMac.HMACSHA256:
                    hmac = new HMACSHA256();
                    break;
                case AeMac.HMACSHA384:
                    hmac = new HMACSHA384();
                    break;
                default:
                    // An algorithm we don't understand
                    throw new CryptographicException();
            }

            // Instead of using the master key directly, derive a key for our chosen
            // HMAC algorithm based upon the master key.
            // Since the output size of the HMAC is the same as the ideal key size for
            // the HMAC, we can use the master key over a fixed input once to perform
            // NIST SP 800-108 5.1 (Counter Mode KDF):
            hmac.Key = masterKey;

            // i=1, Context=ASCII(MAC)
            byte[] newKey = hmac.ComputeHash(new byte[] { 1, 77, 65, 67 });

            hmac.Key = newKey;
            return hmac;
        }

        // A simple helper method to ensure that the offset (writePos) always moves
        // forward with new data.
        private static void Append(byte[] newData, byte[] combinedData, ref int writePos)
        {
            Buffer.BlockCopy(newData, 0, combinedData, writePos, newData.Length);
            writePos += newData.Length;
        }

        /// <summary>
        /// Compare the contents of two arrays in an amount of time which is only
        /// dependent on <paramref name="length"/>.
        /// </summary>
        /// <param name="a">An array to compare to <paramref name="b"/>.</param>
        /// <param name="aOffset">
        /// The starting position within <paramref name="a"/> for comparison.
        /// </param>
        /// <param name="b">An array to compare to <paramref name="a"/>.</param>
        /// <param name="bOffset">
        /// The starting position within <paramref name="b"/> for comparison.
        /// </param>
        /// <param name="length">
        /// The number of bytes to compare between <paramref name="a"/> and
        /// <paramref name="b"/>.</param>
        /// <returns>
        /// <c>true</c> if both <paramref name="a"/> and <paramref name="b"/> have
        /// sufficient length for the comparison and all of the applicable values are the
        /// same in both arrays; <c>false</c> otherwise.
        /// </returns>
        /// <remarks>
        /// An "insufficient data" <c>false</c> response can happen early, but otherwise
        /// a <c>true</c> or <c>false</c> response take the same amount of time.
        /// </remarks>
        [MethodImpl(MethodImplOptions.NoInlining | MethodImplOptions.NoOptimization)]
        private static bool CryptographicEquals(
            byte[] a,
            int aOffset,
            byte[] b,
            int bOffset,
            int length)
        {
            Debug.Assert(a != null);
            Debug.Assert(b != null);
            Debug.Assert(length >= 0);

            int result = 0;

            if (a.Length - aOffset < length || b.Length - bOffset < length)
            {
                return false;
            }

            unchecked
            {
                for (int i = 0; i < length; i++)
                {
                    // Bitwise-OR of subtraction has been found to have the most
                    // stable execution time.
                    //
                    // This cannot overflow because bytes are 1 byte in length, and
                    // result is 4 bytes.
                    // The OR propagates all set bytes, so the differences are only
                    // present in the lowest byte.
                    result = result | (a[i + aOffset] - b[i + bOffset]);
                }
            }

            return result == 0;
        }
    }
}
```
