---
title: CBC 解密漏洞
description: 了解如何使用填充使用密码块链 （CBC） 模式对称解密来检测和缓解计时漏洞。
ms.date: 06/12/2018
author: blowdart
ms.openlocfilehash: 47520ea4c9c7d0ef4d79378c93c6ce1f2ba7dd6d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186096"
---
# <a name="timing-vulnerabilities-with-cbc-mode-symmetric-decryption-using-padding"></a><span data-ttu-id="ba2ab-103">使用填充对 CBC 模式对称解密的漏洞进行计时</span><span class="sxs-lookup"><span data-stu-id="ba2ab-103">Timing vulnerabilities with CBC-mode symmetric decryption using padding</span></span>

<span data-ttu-id="ba2ab-104">Microsoft 认为，在应用可验证填充时，无需首先确保密文的完整性（非常具体的除外），则不再安全地解密使用密码-块链 （CBC） 对称加密模式加密的数据情况 下。</span><span class="sxs-lookup"><span data-stu-id="ba2ab-104">Microsoft believes that it's no longer safe to decrypt data encrypted with the Cipher-Block-Chaining (CBC) mode of symmetric encryption when verifiable padding has been applied without first ensuring the integrity of the ciphertext, except for very specific circumstances.</span></span> <span data-ttu-id="ba2ab-105">这一判断基于目前已知的加密研究。</span><span class="sxs-lookup"><span data-stu-id="ba2ab-105">This judgement is based on currently known cryptographic research.</span></span>

## <a name="introduction"></a><span data-ttu-id="ba2ab-106">介绍</span><span class="sxs-lookup"><span data-stu-id="ba2ab-106">Introduction</span></span>

<span data-ttu-id="ba2ab-107">填充 oracle 攻击是一种针对加密数据的攻击类型，允许攻击者在不知道密钥的情况下解密数据的内容。</span><span class="sxs-lookup"><span data-stu-id="ba2ab-107">A padding oracle attack is a type of attack against encrypted data that allows the attacker to decrypt the contents of the data, without knowing the key.</span></span>

<span data-ttu-id="ba2ab-108">oracle 是指"告诉"，它向攻击者提供有关他们执行的操作是否正确的信息。</span><span class="sxs-lookup"><span data-stu-id="ba2ab-108">An oracle refers to a "tell" which gives an attacker information about whether the action they're executing is correct or not.</span></span> <span data-ttu-id="ba2ab-109">想象一下，和孩子玩棋盘或纸牌游戏。</span><span class="sxs-lookup"><span data-stu-id="ba2ab-109">Imagine playing a board or card game with a child.</span></span> <span data-ttu-id="ba2ab-110">当他们的脸上露出灿烂的笑容，因为他们认为自己要做出一个不错的动作，那是一个神仙。</span><span class="sxs-lookup"><span data-stu-id="ba2ab-110">When their face lights up with a big smile because they think they're about to make a good move, that's an oracle.</span></span> <span data-ttu-id="ba2ab-111">作为对手，您可以使用此预言来适当地规划您的下一步行动。</span><span class="sxs-lookup"><span data-stu-id="ba2ab-111">You, as the opponent, can use this oracle to plan your next move appropriately.</span></span>

<span data-ttu-id="ba2ab-112">填充是一个特定的加密术语。</span><span class="sxs-lookup"><span data-stu-id="ba2ab-112">Padding is a specific cryptographic term.</span></span> <span data-ttu-id="ba2ab-113">某些密码（即用于加密数据的算法）处理数据块，其中每个数据块的大小都是固定大小的。</span><span class="sxs-lookup"><span data-stu-id="ba2ab-113">Some ciphers, which are the algorithms used to encrypt your data, work on blocks of data where each block is a fixed size.</span></span> <span data-ttu-id="ba2ab-114">如果要加密的数据的大小不是填充数据块的正确大小，则将填充数据，直到数据填充为止。</span><span class="sxs-lookup"><span data-stu-id="ba2ab-114">If the data you want to encrypt isn't the right size to fill the blocks, your data is padded until it does.</span></span> <span data-ttu-id="ba2ab-115">许多形式的填充要求填充始终存在，即使原始输入的大小正确。</span><span class="sxs-lookup"><span data-stu-id="ba2ab-115">Many forms of padding require that padding to always be present, even if the original input was of the right size.</span></span> <span data-ttu-id="ba2ab-116">这允许在解密时始终安全地删除填充。</span><span class="sxs-lookup"><span data-stu-id="ba2ab-116">This allows the padding to always be safely removed upon decryption.</span></span>

<span data-ttu-id="ba2ab-117">将两件事情放在一起，带有填充 oracle 的软件实现会显示解密数据是否具有有效的填充。</span><span class="sxs-lookup"><span data-stu-id="ba2ab-117">Putting the two things together, a software implementation with a padding oracle reveals whether decrypted data has valid padding.</span></span> <span data-ttu-id="ba2ab-118">oracle 可以非常简单，例如返回显示"无效填充"的值，或者返回更复杂的值，例如花一个可衡量的不同时间来处理有效的块而不是无效块。</span><span class="sxs-lookup"><span data-stu-id="ba2ab-118">The oracle could be something as simple as returning a value that says "Invalid padding" or something more complicated like taking a measurably different time to process a valid block as opposed to an invalid block.</span></span>

<span data-ttu-id="ba2ab-119">基于块的密码具有另一个属性，称为模式，它确定第一个块中的数据与第二个块中的数据的关系，等等。</span><span class="sxs-lookup"><span data-stu-id="ba2ab-119">Block-based ciphers have another property, called the mode, which determines the relationship of data in the first block to the data in the second block, and so on.</span></span> <span data-ttu-id="ba2ab-120">最常用的模式之一是 CBC。</span><span class="sxs-lookup"><span data-stu-id="ba2ab-120">One of the most commonly used modes is CBC.</span></span> <span data-ttu-id="ba2ab-121">CBC 引入了一个初始随机块，称为初始化矢量 （IV），并将前一个块与静态加密的结果相结合，使其使用相同的密钥加密同一消息并不总是产生相同的加密输出。</span><span class="sxs-lookup"><span data-stu-id="ba2ab-121">CBC introduces an initial random block, known as the Initialization Vector (IV), and combines the previous block with the result of static encryption to make it such that encrypting the same message with the same key doesn't always produce the same encrypted output.</span></span>

<span data-ttu-id="ba2ab-122">攻击者可以使用填充 oracle，结合 CBC 数据的结构化方式，向公开 oracle 的代码发送稍微更改的消息，并持续发送数据，直到 oracle 告诉他们数据正确为止。</span><span class="sxs-lookup"><span data-stu-id="ba2ab-122">An attacker can use a padding oracle, in combination with how CBC data is structured, to send slightly changed messages to the code that exposes the oracle, and keep sending data until the oracle tells them the data is correct.</span></span> <span data-ttu-id="ba2ab-123">通过此响应，攻击者可以解密消息字节字节。</span><span class="sxs-lookup"><span data-stu-id="ba2ab-123">From this response, the attacker can decrypt the message byte by byte.</span></span>

<span data-ttu-id="ba2ab-124">现代计算机网络的质量非常之高，攻击者可以检测到远程系统上的极小（小于 0.1 ms）的执行时间差异。</span><span class="sxs-lookup"><span data-stu-id="ba2ab-124">Modern computer networks are of such high quality that an attacker can detect very small (less than 0.1 ms) differences in execution time on remote systems.</span></span><span data-ttu-id="ba2ab-125">假定成功解密的应用程序只有在数据未被篡改时才能发生，但访问时，很容易受到旨在观察成功解密和不成功解密差异的工具的攻击。</span><span class="sxs-lookup"><span data-stu-id="ba2ab-125"> Applications that are assuming that a successful decryption can only happen when the data wasn't tampered with may be vulnerable to attack from tools that are designed to observe differences in successful and unsuccessful decryption.</span></span> <span data-ttu-id="ba2ab-126">虽然在某些语言或库中，这种时间差异可能比其他语言或库更重要，但现在人们认为，如果考虑到应用程序对失败的响应，这对所有语言和库都是实际威胁。</span><span class="sxs-lookup"><span data-stu-id="ba2ab-126">While this timing difference may be more significant in some languages or libraries than others, it's now believed that this is a practical threat for all languages and libraries when the application's response to failure is taken into account.</span></span>

<span data-ttu-id="ba2ab-127">此攻击依赖于更改加密数据并与 oracle 测试结果的能力。</span><span class="sxs-lookup"><span data-stu-id="ba2ab-127">This attack relies on the ability to change the encrypted data and test the result with the oracle.</span></span> <span data-ttu-id="ba2ab-128">完全缓解攻击的唯一方法是检测加密数据的更改，并拒绝对加密数据执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="ba2ab-128">The only way to fully mitigate the attack is to detect changes to the encrypted data and refuse to perform any actions on it.</span></span> <span data-ttu-id="ba2ab-129">执行此操作的标准方法是为数据创建签名，并在执行任何操作之前验证该签名。</span><span class="sxs-lookup"><span data-stu-id="ba2ab-129">The standard way to do this is to create a signature for the data and validate that signature before any operations are performed.</span></span> <span data-ttu-id="ba2ab-130">签名必须是可验证的，攻击者无法创建签名，否则它们会更改加密数据，然后根据更改的数据计算新签名。</span><span class="sxs-lookup"><span data-stu-id="ba2ab-130">The signature must be verifiable, it cannot be created by the attacker, otherwise they'd change the encrypted data, then compute a new signature based on the changed data.</span></span> <span data-ttu-id="ba2ab-131">一种常见类型的适当签名称为密钥哈希消息身份验证代码 （HMAC）。</span><span class="sxs-lookup"><span data-stu-id="ba2ab-131">One common type of appropriate signature is known as a keyed-hash message authentication code (HMAC).</span></span> <span data-ttu-id="ba2ab-132">HMAC 与校验和不同，因为它需要一个密钥，只有生成 HMAC 的人员和验证者知道。</span><span class="sxs-lookup"><span data-stu-id="ba2ab-132">An HMAC differs from a checksum in that it takes a secret key, known only to the person producing the HMAC and to the person validating it.</span></span> <span data-ttu-id="ba2ab-133">如果没有密钥，您就无法生成正确的 HMAC。</span><span class="sxs-lookup"><span data-stu-id="ba2ab-133">Without possession of the key, you can't produce a correct HMAC.</span></span> <span data-ttu-id="ba2ab-134">收到数据时，您将获取加密数据，使用您和发件人共享的密钥独立计算 HMAC，然后将他们发送的 HMAC 与您计算的 HMAC 进行比较。</span><span class="sxs-lookup"><span data-stu-id="ba2ab-134">When you receive your data, you'd take the encrypted data, independently compute the HMAC using the secret key you and the sender share, then compare the HMAC they sent against the one you computed.</span></span> <span data-ttu-id="ba2ab-135">此比较必须是恒定的时间，否则您添加了另一个可检测的 oracle，允许不同类型的攻击。</span><span class="sxs-lookup"><span data-stu-id="ba2ab-135">This comparison must be constant time, otherwise you've added another detectable oracle, allowing a different type of attack.</span></span>

<span data-ttu-id="ba2ab-136">总之，要安全地使用填充的 CBC 块密码，您必须将它们与 HMAC（或其他数据完整性检查）相结合，在尝试解密数据之前，使用恒定的时间比较进行验证。</span><span class="sxs-lookup"><span data-stu-id="ba2ab-136">In summary, to use padded CBC block ciphers safely, you must combine them with an HMAC (or another data integrity check) that you validate using a constant time comparison before trying to decrypt the data.</span></span> <span data-ttu-id="ba2ab-137">由于所有更改的消息都花费相同的时间生成响应，因此可防止攻击。</span><span class="sxs-lookup"><span data-stu-id="ba2ab-137">Since all altered messages take the same amount time to produce a response, the attack is prevented.</span></span>

## <a name="who-is-vulnerable"></a><span data-ttu-id="ba2ab-138">谁是脆弱的</span><span class="sxs-lookup"><span data-stu-id="ba2ab-138">Who is vulnerable</span></span>

<span data-ttu-id="ba2ab-139">此漏洞适用于执行自己的加密和解密的托管和本机应用程序。</span><span class="sxs-lookup"><span data-stu-id="ba2ab-139">This vulnerability applies to both managed and native applications that are performing their own encryption and decryption.</span></span> <span data-ttu-id="ba2ab-140">这包括：例如：</span><span class="sxs-lookup"><span data-stu-id="ba2ab-140">This includes, for example:</span></span>

- <span data-ttu-id="ba2ab-141">加密 Cookie 以在服务器上稍后解密的应用程序。</span><span class="sxs-lookup"><span data-stu-id="ba2ab-141">An application that encrypts a cookie for later decryption on the server.</span></span>
- <span data-ttu-id="ba2ab-142">一种数据库应用程序，它为用户提供将数据插入到稍后解密列的表中的功能。</span><span class="sxs-lookup"><span data-stu-id="ba2ab-142">A database application that provides the ability for users to insert data into a table whose columns are later decrypted.</span></span>
- <span data-ttu-id="ba2ab-143">一种数据传输应用程序，它使用共享密钥进行加密来保护传输中的数据。</span><span class="sxs-lookup"><span data-stu-id="ba2ab-143">A data transfer application that relies on encryption using a shared key to protect the data in transit.</span></span>
- <span data-ttu-id="ba2ab-144">加密和解密"内部"TLS 隧道中的消息的应用程序。</span><span class="sxs-lookup"><span data-stu-id="ba2ab-144">An application that encrypts and decrypts messages "inside" the TLS tunnel.</span></span>

<span data-ttu-id="ba2ab-145">请注意，在这些情况下，单独使用 TLS 可能无法保护您。</span><span class="sxs-lookup"><span data-stu-id="ba2ab-145">Note that using TLS alone may not protect you in these scenarios.</span></span>

<span data-ttu-id="ba2ab-146">易受攻击的应用程序：</span><span class="sxs-lookup"><span data-stu-id="ba2ab-146">A vulnerable application:</span></span>

- <span data-ttu-id="ba2ab-147">使用具有可验证填充模式的 CBC 密码模式（如 PKCS_7 或 ANSI X.923）解密数据。</span><span class="sxs-lookup"><span data-stu-id="ba2ab-147">Decrypts data using the CBC cipher mode with a verifiable padding mode, such as PKCS#7 or ANSI X.923.</span></span>
- <span data-ttu-id="ba2ab-148">无需执行数据完整性检查（通过 MAC 或非对称数字签名）即可执行解密。</span><span class="sxs-lookup"><span data-stu-id="ba2ab-148">Performs the decryption without having performed a data integrity check (via a MAC or an asymmetric digital signature).</span></span>

<span data-ttu-id="ba2ab-149">这也适用于在这些基元之上构建的抽象之上的应用程序，例如加密消息语法 （PKCS_7/CMS） 包络数据结构。</span><span class="sxs-lookup"><span data-stu-id="ba2ab-149">This also applies to applications built on top of abstractions over top of these primitives, such as the Cryptographic Message Syntax (PKCS#7/CMS) EnvelopedData structure.</span></span>

## <a name="related-areas-of-concern"></a><span data-ttu-id="ba2ab-150">相关关注领域</span><span class="sxs-lookup"><span data-stu-id="ba2ab-150">Related areas of concern</span></span>

<span data-ttu-id="ba2ab-151">研究导致 Microsoft 进一步关注在消息具有众所周知或可预测的页脚结构时，使用 ISO 10126 等效填充填充的 CBC 消息。</span><span class="sxs-lookup"><span data-stu-id="ba2ab-151">Research has led Microsoft to be further concerned about CBC messages that are padded with ISO 10126-equivalent padding when the message has a well-known or predictable footer structure.</span></span> <span data-ttu-id="ba2ab-152">例如，根据 W3C XML 加密语法和处理建议（xmlenc，加密Xml）的规则准备的内容。</span><span class="sxs-lookup"><span data-stu-id="ba2ab-152">For example, content prepared under the rules of the W3C XML Encryption Syntax and Processing Recommendation (xmlenc, EncryptedXml).</span></span> <span data-ttu-id="ba2ab-153">虽然 W3C 在此时对消息进行签名然后加密被认为是适当的，但 Microsoft 现在建议始终执行加密然后签名。</span><span class="sxs-lookup"><span data-stu-id="ba2ab-153">While the W3C guidance to sign the message then encrypt was considered appropriate at the time, Microsoft now recommends always doing encrypt-then-sign.</span></span>

<span data-ttu-id="ba2ab-154">应用程序开发人员应始终注意验证非对称签名密钥的适用性，因为非对称密钥和任意消息之间没有固有的信任关系。</span><span class="sxs-lookup"><span data-stu-id="ba2ab-154">Application developers should always be mindful of verifying the applicability of an asymmetric signature key, as there's no inherent trust relationship between an asymmetric key and an arbitrary message.</span></span>

## <a name="details"></a><span data-ttu-id="ba2ab-155">详细信息</span><span class="sxs-lookup"><span data-stu-id="ba2ab-155">Details</span></span>

<span data-ttu-id="ba2ab-156">从历史上看，人们一致认为，使用 HMAC 或 RSA 签名等手段对重要数据进行加密和身份验证非常重要。</span><span class="sxs-lookup"><span data-stu-id="ba2ab-156">Historically, there has been consensus that it's important to both encrypt and authenticate important data, using means such as HMAC or RSA signatures.</span></span> <span data-ttu-id="ba2ab-157">但是，对于如何对加密和身份验证操作进行排序，没有明确的指导。</span><span class="sxs-lookup"><span data-stu-id="ba2ab-157">However, there has been less clear guidance as to how to sequence the encryption and authentication operations.</span></span> <span data-ttu-id="ba2ab-158">由于本文中详述的漏洞，Microsoft 的指南现在始终使用"加密然后符号"范例。</span><span class="sxs-lookup"><span data-stu-id="ba2ab-158">Due to the vulnerability detailed in this article, Microsoft's guidance is now to always use the "encrypt-then-sign" paradigm.</span></span> <span data-ttu-id="ba2ab-159">也就是说，首先使用对称密钥加密数据，然后通过密文（加密数据）计算 MAC 或非对称签名。</span><span class="sxs-lookup"><span data-stu-id="ba2ab-159">That is, first encrypt data using a symmetric key, then compute a MAC or asymmetric signature over the ciphertext (encrypted data).</span></span> <span data-ttu-id="ba2ab-160">解密数据时，执行相反。</span><span class="sxs-lookup"><span data-stu-id="ba2ab-160">When decrypting data, perform the reverse.</span></span> <span data-ttu-id="ba2ab-161">首先，确认 MAC 或密码文本的签名，然后解密它。</span><span class="sxs-lookup"><span data-stu-id="ba2ab-161">First, confirm the MAC or signature of the ciphertext, then decrypt it.</span></span>

<span data-ttu-id="ba2ab-162">已知存在一类称为"填充 oracle 攻击"的漏洞已有 10 多年的历史。</span><span class="sxs-lookup"><span data-stu-id="ba2ab-162">A class of vulnerabilities known as "padding oracle attacks" have been known to exist for over 10 years.</span></span> <span data-ttu-id="ba2ab-163">这些漏洞允许攻击者使用不超过 4096 次尝试来解密通过对称块算法（如 AES 和 3DES）加密的数据。</span><span class="sxs-lookup"><span data-stu-id="ba2ab-163">These vulnerabilities allow an attacker to decrypt data encrypted by symmetric block algorithms, such as AES and 3DES, using no more than 4096 attempts per block of data.</span></span> <span data-ttu-id="ba2ab-164">这些漏洞利用了阻止密码在末尾最常用与可验证填充数据一起使用这一事实。</span><span class="sxs-lookup"><span data-stu-id="ba2ab-164">These vulnerabilities make use of the fact that block ciphers are most frequently used with verifiable padding data at the end.</span></span> <span data-ttu-id="ba2ab-165">结果发现，如果攻击者可以篡改密文，并找出篡改是否导致末尾填充格式的错误，攻击者可以解密数据。</span><span class="sxs-lookup"><span data-stu-id="ba2ab-165">It was found that if an attacker can tamper with ciphertext and find out whether the tampering caused an error in the format of the padding at the end, the attacker can decrypt the data.</span></span>

<span data-ttu-id="ba2ab-166">最初，实际攻击基于基于填充是否有效的服务返回不同的错误代码，例如ASP.NET漏洞[MS10-070](/security-updates/SecurityBulletins/2010/ms10-070)。</span><span class="sxs-lookup"><span data-stu-id="ba2ab-166">Initially, practical attacks were based on services that would return different error codes based on whether padding was valid, such as the ASP.NET vulnerability [MS10-070](/security-updates/SecurityBulletins/2010/ms10-070).</span></span> <span data-ttu-id="ba2ab-167">但是，Microsoft 现在认为，仅使用处理有效填充和无效填充之间的时间差异进行类似的攻击是切实可行的。</span><span class="sxs-lookup"><span data-stu-id="ba2ab-167">However, Microsoft now believes that it's practical to conduct similar attacks using only the differences in timing between processing valid and invalid padding.</span></span>

<span data-ttu-id="ba2ab-168">如果加密方案使用签名，并且签名验证是在给定数据长度（无论内容如何）使用固定运行时执行的，则可以验证数据完整性，而无需通过[侧通道](https://en.wikipedia.org/wiki/Side-channel_attack)向攻击者发出任何信息。</span><span class="sxs-lookup"><span data-stu-id="ba2ab-168">Provided that the encryption scheme employs a signature and that the signature verification is performed with a fixed runtime for a given length of data (irrespective of the contents), the data integrity can be verified without emitting any information to an attacker via a [side channel](https://en.wikipedia.org/wiki/Side-channel_attack).</span></span> <span data-ttu-id="ba2ab-169">由于完整性检查拒绝任何篡改的消息，因此填充 oracle 威胁得到缓解。</span><span class="sxs-lookup"><span data-stu-id="ba2ab-169">Since the integrity check rejects any tampered messages, the padding oracle threat is mitigated.</span></span>

## <a name="guidance"></a><span data-ttu-id="ba2ab-170">指南</span><span class="sxs-lookup"><span data-stu-id="ba2ab-170">Guidance</span></span>

<span data-ttu-id="ba2ab-171">首先，Microsoft 建议通过传输层安全 （TLS） 传输任何需要保密的数据，这是安全套接字层 （SSL） 的继承者。</span><span class="sxs-lookup"><span data-stu-id="ba2ab-171">First and foremost, Microsoft recommends that any data that has confidentiality needs be transmitted over Transport Layer Security (TLS), the successor to Secure Sockets Layer (SSL).</span></span>

<span data-ttu-id="ba2ab-172">接下来，分析您的应用程序，以便：</span><span class="sxs-lookup"><span data-stu-id="ba2ab-172">Next, analyze your application to:</span></span>

- <span data-ttu-id="ba2ab-173">准确了解您正在执行的加密功能以及正在使用的平台和 API 提供的加密。</span><span class="sxs-lookup"><span data-stu-id="ba2ab-173">Understand precisely what encryption you're performing and what encryption is being provided by the platforms and APIs you're using.</span></span>
- <span data-ttu-id="ba2ab-174">确保在 CBC 模式下，对称[块密码算法](https://en.wikipedia.org/wiki/Block_cipher#Notable_block_ciphers)（如 AES 和 3DES）每一层的每个用法都包含使用密钥键数据完整性检查（非对称签名、HMAC，或将密码模式更改为[经过身份验证的加密](https://en.wikipedia.org/wiki/Authenticated_encryption)（AE） 模式（如 GCM 或 CCM）。</span><span class="sxs-lookup"><span data-stu-id="ba2ab-174">Be certain that each usage at each layer of a symmetric [block cipher algorithm](https://en.wikipedia.org/wiki/Block_cipher#Notable_block_ciphers), such as AES and 3DES, in CBC mode incorporate the use of a secret-keyed data integrity check (an asymmetric signature, an HMAC, or to change the cipher mode to an [authenticated encryption](https://en.wikipedia.org/wiki/Authenticated_encryption) (AE) mode such as GCM or CCM).</span></span>

<span data-ttu-id="ba2ab-175">根据目前的研究，人们普遍认为，当针对非 AE 加密模式独立执行身份验证和加密步骤时，对密码文本（加密然后签名）进行身份验证是最好的常规选项。</span><span class="sxs-lookup"><span data-stu-id="ba2ab-175">Based on the current research, it's generally believed that when the authentication and encryption steps are performed independently for non-AE modes of encryption, authenticating the ciphertext (encrypt-then-sign) is the best general option.</span></span> <span data-ttu-id="ba2ab-176">但是，对于加密学，没有一刀切的正确答案，这种概括不如专业密码学家的定向建议。</span><span class="sxs-lookup"><span data-stu-id="ba2ab-176">However, there's no one-size-fits-all correct answer to cryptography and this generalization isn't as good as directed advice from a professional cryptographer.</span></span>

<span data-ttu-id="ba2ab-177">鼓励无法更改其消息传递格式但执行未经身份验证的 CBC 解密的应用程序尝试合并缓解措施，例如：</span><span class="sxs-lookup"><span data-stu-id="ba2ab-177">Applications that are unable to change their messaging format but perform unauthenticated CBC decryption are encouraged to try to incorporate mitigations such as:</span></span>

- <span data-ttu-id="ba2ab-178">解密，不允许解密器验证或删除填充：</span><span class="sxs-lookup"><span data-stu-id="ba2ab-178">Decrypt without allowing the decryptor to verify or remove padding:</span></span>
  - <span data-ttu-id="ba2ab-179">应用的任何填充仍需要删除或忽略，您将负担转移到应用程序中。</span><span class="sxs-lookup"><span data-stu-id="ba2ab-179">Any padding that was applied still needs to be removed or ignored, you're moving the burden into your application.</span></span>
  - <span data-ttu-id="ba2ab-180">好处是填充验证和删除可以合并到其他应用程序数据验证逻辑中。</span><span class="sxs-lookup"><span data-stu-id="ba2ab-180">The benefit is that the padding verification and removal can be incorporated into other application data verification logic.</span></span> <span data-ttu-id="ba2ab-181">如果填充验证和数据验证可以持续完成，威胁就会减少。</span><span class="sxs-lookup"><span data-stu-id="ba2ab-181">If the padding verification and data verification can be done in constant time, the threat is reduced.</span></span>
  - <span data-ttu-id="ba2ab-182">由于填充的解释会更改感知到的消息长度，因此此方法可能仍发出计时信息。</span><span class="sxs-lookup"><span data-stu-id="ba2ab-182">Since the interpretation of the padding changes the perceived message length, there may still be timing information emitted from this approach.</span></span>
- <span data-ttu-id="ba2ab-183">将解密填充模式更改为 ISO10126：</span><span class="sxs-lookup"><span data-stu-id="ba2ab-183">Change the decryption padding mode to ISO10126:</span></span>
  - <span data-ttu-id="ba2ab-184">ISO10126 解密填充与 PKCS7 加密填充和 ANSIX923 加密填充兼容。</span><span class="sxs-lookup"><span data-stu-id="ba2ab-184">ISO10126 decryption padding is compatible with both PKCS7 encryption padding and ANSIX923 encryption padding.</span></span>
  - <span data-ttu-id="ba2ab-185">更改模式可将填充 oracle 知识减少到 1 个字节，而不是整个块。</span><span class="sxs-lookup"><span data-stu-id="ba2ab-185">Changing the mode reduces the padding oracle knowledge to 1 byte instead of the entire block.</span></span> <span data-ttu-id="ba2ab-186">但是，如果内容具有众所周知的脚法（如关闭的 XML 元素），则相关攻击可以继续攻击消息的其余部分。</span><span class="sxs-lookup"><span data-stu-id="ba2ab-186">However, if the content has a well-known footer, such as a closing XML element, related attacks can continue to attack the rest of the message.</span></span>
  - <span data-ttu-id="ba2ab-187">这也不能阻止纯文本恢复，在这种情况下，攻击者可以强制相同的纯文本加密多次使用不同的消息偏移。</span><span class="sxs-lookup"><span data-stu-id="ba2ab-187">This also doesn't prevent plaintext recovery in situations where the attacker can coerce the same plaintext to be encrypted multiple times with a different message offset.</span></span>
- <span data-ttu-id="ba2ab-188">对解密调用的评估以抑制计时信号：</span><span class="sxs-lookup"><span data-stu-id="ba2ab-188">Gate the evaluation of a decryption call to dampen the timing signal:</span></span>
  - <span data-ttu-id="ba2ab-189">对于包含填充的任何数据段，保持时间的计算必须至少超过解密操作所花费的最大时间。</span><span class="sxs-lookup"><span data-stu-id="ba2ab-189">The computation of hold time must have a minimum in excess of the maximum amount of time the decryption operation would take for any data segment that contains padding.</span></span>
  - <span data-ttu-id="ba2ab-190">时间计算应按照[获取高分辨率时间戳](/windows/desktop/sysinfo/acquiring-high-resolution-time-stamps)的指南进行，而不是通过使用<xref:System.Environment.TickCount?displayProperty=nameWithType>（受滚动/溢出）或减去两个系统时间戳（受 NTP 调整错误约束）。</span><span class="sxs-lookup"><span data-stu-id="ba2ab-190">Time computations should be done according to the guidance in [Acquiring high-resolution time stamps](/windows/desktop/sysinfo/acquiring-high-resolution-time-stamps), not by using <xref:System.Environment.TickCount?displayProperty=nameWithType> (subject to roll-over/overflow) or subtracting two system timestamps (subject to NTP adjustment errors).</span></span>
  - <span data-ttu-id="ba2ab-191">时间计算必须包括解密操作，包括托管或C++应用程序中的所有潜在异常，而不仅仅是填充到末尾。</span><span class="sxs-lookup"><span data-stu-id="ba2ab-191">Time computations must be inclusive of the decryption operation including all potential exceptions in managed or C++ applications, not just padded onto the end.</span></span>
  - <span data-ttu-id="ba2ab-192">如果成功或失败尚未确定，则时序门需要在故障过期时返回故障。</span><span class="sxs-lookup"><span data-stu-id="ba2ab-192">If success or failure has been determined yet, the timing gate needs to return failure when it expires.</span></span>
- <span data-ttu-id="ba2ab-193">执行未经身份验证解密的服务应具有监视位置，以检测大量"无效"消息已通过。</span><span class="sxs-lookup"><span data-stu-id="ba2ab-193">Services that are performing unauthenticated decryption should have monitoring in place to detect that a flood of "invalid" messages has come through.</span></span>
  - <span data-ttu-id="ba2ab-194">请记住，此信号同时包含误报（合法损坏的数据）和假负数（在足够长的时间内展开攻击以逃避检测）。</span><span class="sxs-lookup"><span data-stu-id="ba2ab-194">Bear in mind that this signal carries both false positives (legitimately corrupted data) and false negatives (spreading out the attack over a sufficiently long time to evade detection).</span></span>

## <a name="finding-vulnerable-code---native-applications"></a><span data-ttu-id="ba2ab-195">查找易受攻击的代码 - 本机应用程序</span><span class="sxs-lookup"><span data-stu-id="ba2ab-195">Finding vulnerable code - native applications</span></span>

<span data-ttu-id="ba2ab-196">对于根据 Windows 加密功能构建的程序：下一代 （CNG） 库：</span><span class="sxs-lookup"><span data-stu-id="ba2ab-196">For programs built against the Windows Cryptography: Next Generation (CNG) library:</span></span>

- <span data-ttu-id="ba2ab-197">解密调用是到[BCrypt解密](/windows/desktop/api/bcrypt/nf-bcrypt-bcryptdecrypt)，指定标志`BCRYPT_BLOCK_PADDING`。</span><span class="sxs-lookup"><span data-stu-id="ba2ab-197">The decryption call is to [BCryptDecrypt](/windows/desktop/api/bcrypt/nf-bcrypt-bcryptdecrypt), specifying the `BCRYPT_BLOCK_PADDING` flag.</span></span>
- <span data-ttu-id="ba2ab-198">通过调用[BCryptSetProperty](/windows/desktop/api/bcrypt/nf-bcrypt-bcryptsetproperty)并BCRYPT_CHAINING_MODE[设置为](/windows/desktop/SecCNG/cng-property-identifiers#BCRYPT_CHAINING_MODE)`BCRYPT_CHAIN_MODE_CBC`，已初始化密钥句柄。</span><span class="sxs-lookup"><span data-stu-id="ba2ab-198">The key handle has been initialized by calling [BCryptSetProperty](/windows/desktop/api/bcrypt/nf-bcrypt-bcryptsetproperty) with [BCRYPT_CHAINING_MODE](/windows/desktop/SecCNG/cng-property-identifiers#BCRYPT_CHAINING_MODE) set to `BCRYPT_CHAIN_MODE_CBC`.</span></span>
  - <span data-ttu-id="ba2ab-199">由于`BCRYPT_CHAIN_MODE_CBC`默认值为，受影响的代码可能未为`BCRYPT_CHAINING_MODE`分配任何值。</span><span class="sxs-lookup"><span data-stu-id="ba2ab-199">Since `BCRYPT_CHAIN_MODE_CBC` is the default, affected code may not have assigned any value for `BCRYPT_CHAINING_MODE`.</span></span>

<span data-ttu-id="ba2ab-200">对于根据较旧的 Windows 加密 API 构建的程序：</span><span class="sxs-lookup"><span data-stu-id="ba2ab-200">For programs built against the older Windows Cryptographic API:</span></span>

- <span data-ttu-id="ba2ab-201">解密调用是使用[Crypt 解密](/windows/desktop/api/wincrypt/nf-wincrypt-cryptdecrypt)`Final=TRUE`。</span><span class="sxs-lookup"><span data-stu-id="ba2ab-201">The decryption call is to [CryptDecrypt](/windows/desktop/api/wincrypt/nf-wincrypt-cryptdecrypt) with `Final=TRUE`.</span></span>
- <span data-ttu-id="ba2ab-202">通过调用[CryptSetKeyParam，](/windows/desktop/api/wincrypt/nf-wincrypt-cryptsetkeyparam)将[KP_MODE](/windows/desktop/api/wincrypt/nf-wincrypt-cryptgetkeyparam)设置为`CRYPT_MODE_CBC`，从而初始化了密钥句柄。</span><span class="sxs-lookup"><span data-stu-id="ba2ab-202">The key handle has been initialized by calling [CryptSetKeyParam](/windows/desktop/api/wincrypt/nf-wincrypt-cryptsetkeyparam) with [KP_MODE](/windows/desktop/api/wincrypt/nf-wincrypt-cryptgetkeyparam) set to `CRYPT_MODE_CBC`.</span></span>
  - <span data-ttu-id="ba2ab-203">由于`CRYPT_MODE_CBC`默认值为，受影响的代码可能未为`KP_MODE`分配任何值。</span><span class="sxs-lookup"><span data-stu-id="ba2ab-203">Since `CRYPT_MODE_CBC` is the default, affected code may not have assigned any value for `KP_MODE`.</span></span>

## <a name="finding-vulnerable-code---managed-applications"></a><span data-ttu-id="ba2ab-204">查找易受攻击的代码 - 托管应用程序</span><span class="sxs-lookup"><span data-stu-id="ba2ab-204">Finding vulnerable code - managed applications</span></span>

- <span data-ttu-id="ba2ab-205">解密调用是 或<xref:System.Security.Cryptography.SymmetricAlgorithm.CreateDecryptor>上 上的<xref:System.Security.Cryptography.SymmetricAlgorithm.CreateDecryptor(System.Byte[],System.Byte[])><xref:System.Security.Cryptography.SymmetricAlgorithm?displayProperty=nameWithType>或 上的 方法。</span><span class="sxs-lookup"><span data-stu-id="ba2ab-205">The decryption call is to the <xref:System.Security.Cryptography.SymmetricAlgorithm.CreateDecryptor> or <xref:System.Security.Cryptography.SymmetricAlgorithm.CreateDecryptor(System.Byte[],System.Byte[])> methods on <xref:System.Security.Cryptography.SymmetricAlgorithm?displayProperty=nameWithType>.</span></span>
  - <span data-ttu-id="ba2ab-206">这包括 .NET 中的以下派生类型，但也可能包括第三方类型：</span><span class="sxs-lookup"><span data-stu-id="ba2ab-206">This includes the following derived types within the .NET, but may also include third-party types:</span></span>
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
- <span data-ttu-id="ba2ab-207">属性<xref:System.Security.Cryptography.SymmetricAlgorithm.Padding?displayProperty=nameWithType>设置为<xref:System.Security.Cryptography.PaddingMode.PKCS7?displayProperty=nameWithType>或<xref:System.Security.Cryptography.PaddingMode.ANSIX923?displayProperty=nameWithType>。 <xref:System.Security.Cryptography.PaddingMode.ISO10126?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="ba2ab-207">The <xref:System.Security.Cryptography.SymmetricAlgorithm.Padding?displayProperty=nameWithType> property was set to <xref:System.Security.Cryptography.PaddingMode.PKCS7?displayProperty=nameWithType>, <xref:System.Security.Cryptography.PaddingMode.ANSIX923?displayProperty=nameWithType>, or <xref:System.Security.Cryptography.PaddingMode.ISO10126?displayProperty=nameWithType>.</span></span>
  - <span data-ttu-id="ba2ab-208">由于<xref:System.Security.Cryptography.PaddingMode.PKCS7?displayProperty=nameWithType>默认为，受影响的代码可能从未分配过该<xref:System.Security.Cryptography.SymmetricAlgorithm.Padding?displayProperty=nameWithType>属性。</span><span class="sxs-lookup"><span data-stu-id="ba2ab-208">Since <xref:System.Security.Cryptography.PaddingMode.PKCS7?displayProperty=nameWithType> is the default, affected code may never have assigned the <xref:System.Security.Cryptography.SymmetricAlgorithm.Padding?displayProperty=nameWithType> property.</span></span>
- <span data-ttu-id="ba2ab-209">属性<xref:System.Security.Cryptography.SymmetricAlgorithm.Mode?displayProperty=nameWithType>设置为<xref:System.Security.Cryptography.CipherMode.CBC?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="ba2ab-209">The <xref:System.Security.Cryptography.SymmetricAlgorithm.Mode?displayProperty=nameWithType> property was set to <xref:System.Security.Cryptography.CipherMode.CBC?displayProperty=nameWithType></span></span>
  - <span data-ttu-id="ba2ab-210">由于<xref:System.Security.Cryptography.CipherMode.CBC?displayProperty=nameWithType>默认为，受影响的代码可能从未分配过该<xref:System.Security.Cryptography.SymmetricAlgorithm.Mode?displayProperty=nameWithType>属性。</span><span class="sxs-lookup"><span data-stu-id="ba2ab-210">Since <xref:System.Security.Cryptography.CipherMode.CBC?displayProperty=nameWithType> is the default, affected code may never have assigned the <xref:System.Security.Cryptography.SymmetricAlgorithm.Mode?displayProperty=nameWithType> property.</span></span>

## <a name="finding-vulnerable-code---cryptographic-message-syntax"></a><span data-ttu-id="ba2ab-211">查找易受攻击的代码 - 加密消息语法</span><span class="sxs-lookup"><span data-stu-id="ba2ab-211">Finding vulnerable code - cryptographic message syntax</span></span>

<span data-ttu-id="ba2ab-212">未经身份验证的 CMS EnvelopedData 消息，其加密内容使用 AES 的 CBC 模式 （2.16.840.1.1.101.3.4.1.2， 2.16.840.1.1.1.3.4.1.22， 2.16.840.1.101.3.4.1.42）、DES （1.3.14.3.2.7）、3DES（1.2.840.113549.3.7）或 RC2 （1.2.840.113549.3.2）易受攻击，以及在 CBC 模式下使用任何其他块密码算法的消息。</span><span class="sxs-lookup"><span data-stu-id="ba2ab-212">An unauthenticated CMS EnvelopedData message whose encrypted content uses the CBC mode of AES (2.16.840.1.101.3.4.1.2, 2.16.840.1.101.3.4.1.22, 2.16.840.1.101.3.4.1.42), DES (1.3.14.3.2.7), 3DES (1.2.840.113549.3.7) or RC2 (1.2.840.113549.3.2) is vulnerable, as well as messages using any other block cipher algorithms in CBC mode.</span></span>

<span data-ttu-id="ba2ab-213">虽然流密码不受此特定漏洞的影响，但 Microsoft 建议始终通过检查 Content加密算法值来验证数据。</span><span class="sxs-lookup"><span data-stu-id="ba2ab-213">While stream ciphers aren't susceptible to this particular vulnerability, Microsoft recommends always authenticating the data over inspecting the ContentEncryptionAlgorithm value.</span></span>

<span data-ttu-id="ba2ab-214">对于托管应用程序，可以将 CMS EnvelopedData blob 检测为传递给<xref:System.Security.Cryptography.Pkcs.EnvelopedCms.Decode(System.Byte[])?displayProperty=fullName>的任何值。</span><span class="sxs-lookup"><span data-stu-id="ba2ab-214">For managed applications, a CMS EnvelopedData blob can be detected as any value that is passed to <xref:System.Security.Cryptography.Pkcs.EnvelopedCms.Decode(System.Byte[])?displayProperty=fullName>.</span></span>

<span data-ttu-id="ba2ab-215">对于本机应用程序，CMS EnvelopedData blob 可以检测为通过[CryptMgUpdate](/windows/desktop/api/wincrypt/nf-wincrypt-cryptmsgupdate)提供给 CMS 句柄的任何[CMSG_TYPE_PARAM](/windows/desktop/api/wincrypt/nf-wincrypt-cryptmsggetparam)值，`CMSG_ENVELOPED`其生成的CMSG_TYPE_PARAM是和/或 CMS`CMSG_CTRL_DECRYPT`句柄，稍后通过[CryptMgControl](/windows/desktop/api/wincrypt/nf-wincrypt-cryptmsgcontrol)发送指令。</span><span class="sxs-lookup"><span data-stu-id="ba2ab-215">For native applications, a CMS EnvelopedData blob can be detected as any value provided to a CMS handle via [CryptMsgUpdate](/windows/desktop/api/wincrypt/nf-wincrypt-cryptmsgupdate) whose resulting [CMSG_TYPE_PARAM](/windows/desktop/api/wincrypt/nf-wincrypt-cryptmsggetparam) is `CMSG_ENVELOPED` and/or the CMS handle is later sent a `CMSG_CTRL_DECRYPT` instruction via [CryptMsgControl](/windows/desktop/api/wincrypt/nf-wincrypt-cryptmsgcontrol).</span></span>

## <a name="vulnerable-code-example---managed"></a><span data-ttu-id="ba2ab-216">易受攻击的代码示例 - 托管</span><span class="sxs-lookup"><span data-stu-id="ba2ab-216">Vulnerable code example - managed</span></span>

<span data-ttu-id="ba2ab-217">此方法读取 Cookie 并对其进行解密，并且数据完整性检查不可见。</span><span class="sxs-lookup"><span data-stu-id="ba2ab-217">This method reads a cookie and decrypts it and no data integrity check is visible.</span></span> <span data-ttu-id="ba2ab-218">因此，此方法读取的 Cookie 的内容可能会由接收该 Cookie 的用户或任何获得加密 Cookie 值的攻击者攻击。</span><span class="sxs-lookup"><span data-stu-id="ba2ab-218">Therefore, the contents of a cookie that is read by this method can be attacked by the user who received it, or by any attacker who has obtained the encrypted cookie value.</span></span>

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

## <a name="example-code-following-recommended-practices---managed"></a><span data-ttu-id="ba2ab-219">建议的做法示例代码 - 托管</span><span class="sxs-lookup"><span data-stu-id="ba2ab-219">Example code following recommended practices - managed</span></span>

<span data-ttu-id="ba2ab-220">以下示例代码使用非标准消息格式</span><span class="sxs-lookup"><span data-stu-id="ba2ab-220">The following sample code uses a non-standard message format of</span></span>

`cipher_algorithm_id || hmac_algorithm_id || hmac_tag || iv || ciphertext`

<span data-ttu-id="ba2ab-221">其中`cipher_algorithm_id`和`hmac_algorithm_id`算法标识符是这些算法的应用程序本地（非标准）表示形式。</span><span class="sxs-lookup"><span data-stu-id="ba2ab-221">where the `cipher_algorithm_id` and `hmac_algorithm_id` algorithm identifiers are application-local (non-standard) representations of those algorithms.</span></span> <span data-ttu-id="ba2ab-222">这些标识符在现有消息传递协议的其他部分可能有意义，而不是作为裸联字节流。</span><span class="sxs-lookup"><span data-stu-id="ba2ab-222">These identifiers may make sense in other parts of your existing messaging protocol instead of as a bare concatenated bytestream.</span></span>

<span data-ttu-id="ba2ab-223">此示例还使用单个主密钥派生加密密钥和 HMAC 密钥。</span><span class="sxs-lookup"><span data-stu-id="ba2ab-223">This example also uses a single master key to derive both an encryption key and an HMAC key.</span></span> <span data-ttu-id="ba2ab-224">这既便于将单键应用程序转换为双键应用程序，又鼓励将两个键保留为不同的值。</span><span class="sxs-lookup"><span data-stu-id="ba2ab-224">This is provided both as a convenience for turning a singly-keyed application into a dual-keyed application, and to encourage keeping the two keys as different values.</span></span> <span data-ttu-id="ba2ab-225">它还保证 HMAC 密钥和加密密钥不能出同步。</span><span class="sxs-lookup"><span data-stu-id="ba2ab-225">It further guarantees that the HMAC key and encryption key can't get out of synchronization.</span></span>

<span data-ttu-id="ba2ab-226">此示例不接受加密或解密的<xref:System.IO.Stream>。</span><span class="sxs-lookup"><span data-stu-id="ba2ab-226">This sample doesn't accept a <xref:System.IO.Stream> for either encryption or decryption.</span></span> <span data-ttu-id="ba2ab-227">当前数据格式使单路加密变得困难，`hmac_tag`因为值位于密文之前。</span><span class="sxs-lookup"><span data-stu-id="ba2ab-227">The current data format makes one-pass encrypt difficult because the `hmac_tag` value precedes the ciphertext.</span></span> <span data-ttu-id="ba2ab-228">但是，之所以选择此格式，是因为它使所有固定大小的元素在开始时保持简单。</span><span class="sxs-lookup"><span data-stu-id="ba2ab-228">However, this format was chosen because it keeps all of the fixed-size elements at the beginning to keep the parser simpler.</span></span> <span data-ttu-id="ba2ab-229">使用此数据格式，可以进行一次性解密，但被警告实施者在调用 TransformFinalBlock 之前调用 GetHashAndReset 并验证结果。</span><span class="sxs-lookup"><span data-stu-id="ba2ab-229">With this data format, one-pass decrypt is possible, though an implementer is cautioned to call GetHashAndReset and verify the result before calling TransformFinalBlock.</span></span> <span data-ttu-id="ba2ab-230">如果流加密很重要，则可能需要其他 AE 模式。</span><span class="sxs-lookup"><span data-stu-id="ba2ab-230">If streaming encryption is important, then a different AE mode may be required.</span></span>

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
