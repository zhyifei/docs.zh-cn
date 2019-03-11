---
title: Certmgr.exe（证书管理器工具）
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- certificates, managing
- CRLs
- certificate trust lists
- Certmgr.exe
- Certificate Manager tool
- CTLs
- certificate revocation lists
ms.assetid: 7e953b43-1374-4bbc-814f-53ca1b6b52bb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: eceff4380fa5965ef38fb98f4ead81b052da3460
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57496919"
---
# <a name="certmgrexe-certificate-manager-tool"></a><span data-ttu-id="a49f4-102">Certmgr.exe（证书管理器工具）</span><span class="sxs-lookup"><span data-stu-id="a49f4-102">Certmgr.exe (Certificate Manager Tool)</span></span>
<span data-ttu-id="a49f4-103">证书管理器工具 (Certmgr.exe) 管理证书、证书信任列表 (CTL) 和证书吊销列表 (CRL)。</span><span class="sxs-lookup"><span data-stu-id="a49f4-103">The Certificate Manager tool (Certmgr.exe) manages certificates, certificate trust lists (CTLs), and certificate revocation lists (CRLs).</span></span>  
  
 <span data-ttu-id="a49f4-104">安装 Visual Studio 时，将会自动安装证书管理器。</span><span class="sxs-lookup"><span data-stu-id="a49f4-104">The Certificate Manager is automatically installed with Visual Studio.</span></span> <span data-ttu-id="a49f4-105">若要启动该工具，请使用[命令提示](../../../docs/framework/tools/developer-command-prompt-for-vs.md)。</span><span class="sxs-lookup"><span data-stu-id="a49f4-105">To start the tool, use the [Command Prompts](../../../docs/framework/tools/developer-command-prompt-for-vs.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a49f4-106">证书管理器工具 (Certmgr.exe) 是命令行实用程序，而“证书”(Certmgr.msc) 则是 Microsoft 管理控制台 (MMC) 管理单元。</span><span class="sxs-lookup"><span data-stu-id="a49f4-106">The Certificate Manager tool (Certmgr.exe) is a command-line utility, whereas Certificates (Certmgr.msc) is a Microsoft Management Console (MMC) snap-in.</span></span> <span data-ttu-id="a49f4-107">由于 Certmgr.msc 通常位于 Windows 系统目录中，因此在命令行上输入 `certmgr` 可加载“证书”MMC 管理单元（即使已打开 Visual Studio 开发人员命令提示）。</span><span class="sxs-lookup"><span data-stu-id="a49f4-107">Because Certmgr.msc is usually found in the Windows System directory, entering `certmgr` at the command line may load the Certificates MMC snap-in even if you have opened the Developer Command Prompt for Visual Studio.</span></span> <span data-ttu-id="a49f4-108">出现这种情况的原因是，在 PATH 环境变量中，“证书”管理单元的路径出现在证书管理器工具的路径之前。</span><span class="sxs-lookup"><span data-stu-id="a49f4-108">This occurs because the path to the snap-in precedes the path to the Certificate Manager tool in the PATH environment variable.</span></span> <span data-ttu-id="a49f4-109">如果你遇到此问题，则可以通过指定可执行文件的路径来执行 Certmgr.exe 命令。</span><span class="sxs-lookup"><span data-stu-id="a49f4-109">If you encounter this problem, you can execute Certmgr.exe commands by specifying the path to the executable.</span></span>  
  
 <span data-ttu-id="a49f4-110">此工具会自动随 Visual Studio 一起安装。</span><span class="sxs-lookup"><span data-stu-id="a49f4-110">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="a49f4-111">若要运行此工具，请使用 Visual Studio 开发人员命令提示（或 Windows 7 中的 Visual Studio 命令提示）。</span><span class="sxs-lookup"><span data-stu-id="a49f4-111">To run the tool, use the Developer Command Prompt for Visual Studio (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="a49f4-112">有关详细信息，请参阅[命令提示](../../../docs/framework/tools/developer-command-prompt-for-vs.md)。</span><span class="sxs-lookup"><span data-stu-id="a49f4-112">For more information, see [Command Prompts](../../../docs/framework/tools/developer-command-prompt-for-vs.md).</span></span>  
  
 <span data-ttu-id="a49f4-113">有关 X.509 证书的概述，请参阅[使用证书](../../../docs/framework/wcf/feature-details/working-with-certificates.md)。</span><span class="sxs-lookup"><span data-stu-id="a49f4-113">For an overview of X.509 certificates, see [Working with Certificates](../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span>  
  
 <span data-ttu-id="a49f4-114">在命令提示符处，键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="a49f4-114">At the command prompt, type the following:</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a49f4-115">语法</span><span class="sxs-lookup"><span data-stu-id="a49f4-115">Syntax</span></span>  
  
```  
      certmgr [/add | /del | /put] [options]  
[/s[/r registryLocation]] [sourceStorename]  
[/s[/r registryLocation]] [destinationStorename]  
```  
  
## <a name="parameters"></a><span data-ttu-id="a49f4-116">参数</span><span class="sxs-lookup"><span data-stu-id="a49f4-116">Parameters</span></span>  
  
|<span data-ttu-id="a49f4-117">参数</span><span class="sxs-lookup"><span data-stu-id="a49f4-117">Argument</span></span>|<span data-ttu-id="a49f4-118">说明</span><span class="sxs-lookup"><span data-stu-id="a49f4-118">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="a49f4-119">*sourceStorename*</span><span class="sxs-lookup"><span data-stu-id="a49f4-119">*sourceStorename*</span></span>|<span data-ttu-id="a49f4-120">包含要添加、删除、保存或显示的现有证书、CTL 或 CRL 的证书存储。</span><span class="sxs-lookup"><span data-stu-id="a49f4-120">The certificate store that contains the existing certificates, CTLs, or CRLs to add, delete, save, or display.</span></span> <span data-ttu-id="a49f4-121">这可以是一个存储文件，也可以是一个系统存储。</span><span class="sxs-lookup"><span data-stu-id="a49f4-121">This can be a store file or a systems store.</span></span>|  
|<span data-ttu-id="a49f4-122">*destinationStorename*</span><span class="sxs-lookup"><span data-stu-id="a49f4-122">*destinationStorename*</span></span>|<span data-ttu-id="a49f4-123">输出证书存储或文件。</span><span class="sxs-lookup"><span data-stu-id="a49f4-123">The output certificate store or file.</span></span>|  
  
|<span data-ttu-id="a49f4-124">选项</span><span class="sxs-lookup"><span data-stu-id="a49f4-124">Option</span></span>|<span data-ttu-id="a49f4-125">说明</span><span class="sxs-lookup"><span data-stu-id="a49f4-125">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="a49f4-126">**/add**</span><span class="sxs-lookup"><span data-stu-id="a49f4-126">**/add**</span></span>|<span data-ttu-id="a49f4-127">将证书、CTL 和 CRL 添加到证书存储中。</span><span class="sxs-lookup"><span data-stu-id="a49f4-127">Adds certificates, CTLs, and CRLs to a certificate store.</span></span>|  
|<span data-ttu-id="a49f4-128">**/all**</span><span class="sxs-lookup"><span data-stu-id="a49f4-128">**/all**</span></span>|<span data-ttu-id="a49f4-129">当与 **/add** 一起使用时添加所有项。</span><span class="sxs-lookup"><span data-stu-id="a49f4-129">Adds all entries when used with **/add**.</span></span> <span data-ttu-id="a49f4-130">当与 **/del** 一起使用时删除所有项。当不与 **/add** 或 **/del** 选项一起使用时显示所有项。</span><span class="sxs-lookup"><span data-stu-id="a49f4-130">Deletes all entries when used with **/del**. Displays all entries when used without the **/add** or **/del** options.</span></span> <span data-ttu-id="a49f4-131">**/all** 选项不能与 **/put** 一起使用。</span><span class="sxs-lookup"><span data-stu-id="a49f4-131">The **/all** option cannot be used with **/put**.</span></span>|  
|<span data-ttu-id="a49f4-132">**/c**</span><span class="sxs-lookup"><span data-stu-id="a49f4-132">**/c**</span></span>|<span data-ttu-id="a49f4-133">当与 **/add** 一起使用时添加证书。</span><span class="sxs-lookup"><span data-stu-id="a49f4-133">Adds certificates when used with **/add**.</span></span> <span data-ttu-id="a49f4-134">当与 **/del** 一起使用时删除证书。当与 **/put** 一起使用时保存证书。</span><span class="sxs-lookup"><span data-stu-id="a49f4-134">Deletes certificates when used with **/del**. Saves certificates when used with **/put**.</span></span> <span data-ttu-id="a49f4-135">当不与 **/add**、**/del** 或 **/put** 选项一起使用时显示证书。</span><span class="sxs-lookup"><span data-stu-id="a49f4-135">Displays certificates when used without the **/add**, **/del**, or **/put** option.</span></span>|  
|<span data-ttu-id="a49f4-136">**/CRL**</span><span class="sxs-lookup"><span data-stu-id="a49f4-136">**/CRL**</span></span>|<span data-ttu-id="a49f4-137">当与 **/add** 一起使用时添加 CRL。</span><span class="sxs-lookup"><span data-stu-id="a49f4-137">Adds CRLs when used with **/add**.</span></span> <span data-ttu-id="a49f4-138">当与 **/del** 一起使用时删除 CRL。当与 **/put** 一起使用时保存 CRL。</span><span class="sxs-lookup"><span data-stu-id="a49f4-138">Deletes CRLs when used with **/del**. Saves CRLs when used with **/put**.</span></span> <span data-ttu-id="a49f4-139">当不与 **/add**、**/del** 或 **/put** 选项一起使用时显示 CRL。</span><span class="sxs-lookup"><span data-stu-id="a49f4-139">Displays CRLs when used without the **/add**, **/del**, or **/put** option.</span></span>|  
|<span data-ttu-id="a49f4-140">**/CTL**</span><span class="sxs-lookup"><span data-stu-id="a49f4-140">**/CTL**</span></span>|<span data-ttu-id="a49f4-141">当与 **/add** 一起使用时添加 CTL。</span><span class="sxs-lookup"><span data-stu-id="a49f4-141">Adds CTLs when used with **/add**.</span></span> <span data-ttu-id="a49f4-142">当与 **/del** 一起使用时删除 CTL。当与 **/put** 一起使用时保存 CTL。</span><span class="sxs-lookup"><span data-stu-id="a49f4-142">Deletes CTLs when used with **/del**. Saves CTLs when used with **/put**.</span></span> <span data-ttu-id="a49f4-143">当不与 **/add**、**/del** 或 **/put** 选项一起使用时显示 CTL。</span><span class="sxs-lookup"><span data-stu-id="a49f4-143">Displays CTLs when used without the **/add**, **/del**, or **/put** option.</span></span>|  
|<span data-ttu-id="a49f4-144">**/del**</span><span class="sxs-lookup"><span data-stu-id="a49f4-144">**/del**</span></span>|<span data-ttu-id="a49f4-145">从证书存储中删除证书、CTL 和 CRL。</span><span class="sxs-lookup"><span data-stu-id="a49f4-145">Deletes certificates, CTLs, and CRLs from a certificate store.</span></span>|  
|<span data-ttu-id="a49f4-146">**/e** *encodingType*</span><span class="sxs-lookup"><span data-stu-id="a49f4-146">**/e** *encodingType*</span></span>|<span data-ttu-id="a49f4-147">指定证书编码类型。</span><span class="sxs-lookup"><span data-stu-id="a49f4-147">Specifies the certificate encoding type.</span></span> <span data-ttu-id="a49f4-148">默认值为 `X509_ASN_ENCODING`。</span><span class="sxs-lookup"><span data-stu-id="a49f4-148">The default is `X509_ASN_ENCODING`.</span></span>|  
|<span data-ttu-id="a49f4-149">**/f** *dwFlags*</span><span class="sxs-lookup"><span data-stu-id="a49f4-149">**/f** *dwFlags*</span></span>|<span data-ttu-id="a49f4-150">指定存储打开标志。</span><span class="sxs-lookup"><span data-stu-id="a49f4-150">Specifies the store open flag.</span></span> <span data-ttu-id="a49f4-151">这是传递到 **CertOpenStore** 的 *dwFlags* 参数。</span><span class="sxs-lookup"><span data-stu-id="a49f4-151">This is the *dwFlags* parameter passed to **CertOpenStore**.</span></span> <span data-ttu-id="a49f4-152">默认值为 CERT_SYSTEM_STORE_CURRENT_USER。</span><span class="sxs-lookup"><span data-stu-id="a49f4-152">The default value is CERT_SYSTEM_STORE_CURRENT_USER.</span></span> <span data-ttu-id="a49f4-153">仅当使用 **/y** 选项时才考虑此选项。</span><span class="sxs-lookup"><span data-stu-id="a49f4-153">This option is considered only if the **/y** option is used.</span></span>|  
|<span data-ttu-id="a49f4-154">**/h**[**elp**]</span><span class="sxs-lookup"><span data-stu-id="a49f4-154">**/h**[**elp**]</span></span>|<span data-ttu-id="a49f4-155">显示该工具的命令语法和选项。</span><span class="sxs-lookup"><span data-stu-id="a49f4-155">Displays command syntax and options for the tool.</span></span>|  
|<span data-ttu-id="a49f4-156">**/n** *nam*</span><span class="sxs-lookup"><span data-stu-id="a49f4-156">**/n** *nam*</span></span>|<span data-ttu-id="a49f4-157">指定要添加、删除或保存的证书的公用名。</span><span class="sxs-lookup"><span data-stu-id="a49f4-157">Specifies the common name of the certificate to add, delete, or save.</span></span> <span data-ttu-id="a49f4-158">此选项只能用于证书，不能用于 CTL 或 CRL。</span><span class="sxs-lookup"><span data-stu-id="a49f4-158">This option can only be used with certificates; it cannot be used with CTLs or CRLs.</span></span>|  
|<span data-ttu-id="a49f4-159">**/put**</span><span class="sxs-lookup"><span data-stu-id="a49f4-159">**/put**</span></span>|<span data-ttu-id="a49f4-160">将证书存储中的 X.509 证书、CTL 或 CRL 保存到文件。</span><span class="sxs-lookup"><span data-stu-id="a49f4-160">Saves an X.509 certificate, CTL, or CRL from a certificate store to a file.</span></span> <span data-ttu-id="a49f4-161">文件以 X.509 格式保存。</span><span class="sxs-lookup"><span data-stu-id="a49f4-161">The file is saved in X.509 format.</span></span> <span data-ttu-id="a49f4-162">**/7** 选项可与 **/put** 选项一起使用，以便用 PKCS #7 格式保存文件。</span><span class="sxs-lookup"><span data-stu-id="a49f4-162">You can use the **/7** option with the **/put** option to save the file in PKCS #7 format.</span></span> <span data-ttu-id="a49f4-163">**/put** 选项后面必须有 **/c**、**/CTL** 或 **/CRL**。</span><span class="sxs-lookup"><span data-stu-id="a49f4-163">The **/put** option must be followed by either **/c**, **/CTL**, or **/CRL**.</span></span> <span data-ttu-id="a49f4-164">**/all** 选项不能与 **/put** 一起使用。</span><span class="sxs-lookup"><span data-stu-id="a49f4-164">The **/all** option cannot be used with **/put**.</span></span>|  
|<span data-ttu-id="a49f4-165">**/r** *location*</span><span class="sxs-lookup"><span data-stu-id="a49f4-165">**/r** *location*</span></span>|<span data-ttu-id="a49f4-166">标识系统存储的注册表位置。</span><span class="sxs-lookup"><span data-stu-id="a49f4-166">Identifies the registry location of the system store.</span></span> <span data-ttu-id="a49f4-167">仅当指定 **/s** 选项时才考虑此选项。</span><span class="sxs-lookup"><span data-stu-id="a49f4-167">This option is considered only if you specify the **/s** option.</span></span> <span data-ttu-id="a49f4-168">*location* 必须是以下项之一：</span><span class="sxs-lookup"><span data-stu-id="a49f4-168">*location* must be one of the following:</span></span><br /><br /> <span data-ttu-id="a49f4-169">-   `currentUser` 指示证书存储在 HKEY_CURRENT_USER 项下。</span><span class="sxs-lookup"><span data-stu-id="a49f4-169">-   `currentUser` indicates that the certificate store is under the HKEY_CURRENT_USER key.</span></span> <span data-ttu-id="a49f4-170">这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="a49f4-170">This is the default.</span></span><br /><span data-ttu-id="a49f4-171">-   `localMachine` 指示证书存储在 HKEY_LOCAL_MACHINE 项下。</span><span class="sxs-lookup"><span data-stu-id="a49f4-171">-   `localMachine` indicates that the certificate store is under the HKEY_LOCAL_MACHINE key.</span></span>|  
|<span data-ttu-id="a49f4-172">**/s**</span><span class="sxs-lookup"><span data-stu-id="a49f4-172">**/s**</span></span>|<span data-ttu-id="a49f4-173">指示证书存储是系统存储。</span><span class="sxs-lookup"><span data-stu-id="a49f4-173">Indicates that the certificate store is a system store.</span></span> <span data-ttu-id="a49f4-174">如果未指定此选项，则会将存储视为 **StoreFile**。</span><span class="sxs-lookup"><span data-stu-id="a49f4-174">If you do not specify this option, the store is considered to be a **StoreFile**.</span></span>|  
|<span data-ttu-id="a49f4-175">**/sha1** *sha1Hash*</span><span class="sxs-lookup"><span data-stu-id="a49f4-175">**/sha1** *sha1Hash*</span></span>|<span data-ttu-id="a49f4-176">指定要添加、删除或保存的证书、CTL 或 CRL 的 SHA1 哈希。</span><span class="sxs-lookup"><span data-stu-id="a49f4-176">Specifies the SHA1 hash of the certificate, CTL, or CRL to add, delete, or save.</span></span>|  
|<span data-ttu-id="a49f4-177">**/v**</span><span class="sxs-lookup"><span data-stu-id="a49f4-177">**/v**</span></span>|<span data-ttu-id="a49f4-178">指定详细模式；显示有关证书、CTL 和 CRL 的详细信息。</span><span class="sxs-lookup"><span data-stu-id="a49f4-178">Specifies verbose mode; displays detailed information about certificates, CTLs, and CRLs.</span></span> <span data-ttu-id="a49f4-179">此选项不能与 **/add**、**/del** 或 **/put** 选项一起使用。</span><span class="sxs-lookup"><span data-stu-id="a49f4-179">This option cannot be used with the **/add**, **/del**, or **/put** options.</span></span>|  
|<span data-ttu-id="a49f4-180">**/y** *provider*</span><span class="sxs-lookup"><span data-stu-id="a49f4-180">**/y** *provider*</span></span>|<span data-ttu-id="a49f4-181">指定存储提供程序名称。</span><span class="sxs-lookup"><span data-stu-id="a49f4-181">Specifies the store provider name.</span></span>|  
|<span data-ttu-id="a49f4-182">**/7**</span><span class="sxs-lookup"><span data-stu-id="a49f4-182">**/7**</span></span>|<span data-ttu-id="a49f4-183">将目标存储保存为 PKCS #7 对象。</span><span class="sxs-lookup"><span data-stu-id="a49f4-183">Saves the destination store as a PKCS #7 object.</span></span>|  
|<span data-ttu-id="a49f4-184">**/?**</span><span class="sxs-lookup"><span data-stu-id="a49f4-184">**/?**</span></span>|<span data-ttu-id="a49f4-185">显示该工具的命令语法和选项。</span><span class="sxs-lookup"><span data-stu-id="a49f4-185">Displays command syntax and options for the tool.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a49f4-186">备注</span><span class="sxs-lookup"><span data-stu-id="a49f4-186">Remarks</span></span>  
 <span data-ttu-id="a49f4-187">Certmgr.exe 执行下列基本功能：</span><span class="sxs-lookup"><span data-stu-id="a49f4-187">Certmgr.exe performs the following basic functions:</span></span>  
  
-   <span data-ttu-id="a49f4-188">将证书、CTL 和 CRL 显示到控制台。</span><span class="sxs-lookup"><span data-stu-id="a49f4-188">Displays certificates, CTLs, and CRLs to the console.</span></span>  
  
-   <span data-ttu-id="a49f4-189">将证书、CTL 和 CRL 添加到证书存储中。</span><span class="sxs-lookup"><span data-stu-id="a49f4-189">Adds certificates, CTLs, and CRLs to a certificate store.</span></span>  
  
-   <span data-ttu-id="a49f4-190">从证书存储中删除证书、CTL 和 CRL。</span><span class="sxs-lookup"><span data-stu-id="a49f4-190">Deletes certificates, CTLs, and CRLs from a certificate store.</span></span>  
  
-   <span data-ttu-id="a49f4-191">将证书存储中的 X.509 证书、CTL 或 CRL 保存到文件。</span><span class="sxs-lookup"><span data-stu-id="a49f4-191">Saves an X.509 certificate, CTL, or CRL from a certificate store to a file.</span></span>  
  
 <span data-ttu-id="a49f4-192">Certmgr.exe 适用于两类证书存储：StoreFile 和系统存储。</span><span class="sxs-lookup"><span data-stu-id="a49f4-192">Certmgr.exe works with two types of certificate stores: **StoreFile** and system store.</span></span> <span data-ttu-id="a49f4-193">不必指定证书存储的类型；Certmgr.exe 能够识别存储类型并执行适当的操作。</span><span class="sxs-lookup"><span data-stu-id="a49f4-193">It is not necessary to specify the type of certificate store; Certmgr.exe can identify the store type and perform the appropriate operations.</span></span>  
  
 <span data-ttu-id="a49f4-194">运行 Certmgr.exe 时若不指定任何选项，则将启动 certmgr.msc 管理单元，该管理单元具有一个 GUI，可帮助执行也可通过命令行访问的证书管理任务。</span><span class="sxs-lookup"><span data-stu-id="a49f4-194">Running Certmgr.exe without specifying any options launches the certmgr.msc snap-in, which has a GUI that helps with the certificate management tasks that are also available from the command line.</span></span> <span data-ttu-id="a49f4-195">该 GUI 提供了一个导入向导，此向导会将证书、CTL 和 CRL 从磁盘复制到证书存储中。</span><span class="sxs-lookup"><span data-stu-id="a49f4-195">The GUI provides an import wizard, which copies certificates, CTLs, and CRLs from your disk to a certificate store.</span></span>  
  
 <span data-ttu-id="a49f4-196">可以通过编译并运行以下代码来找到 `sourceStorename` 和 `destinationStorename` 参数的 X509 证书存储的名称。</span><span class="sxs-lookup"><span data-stu-id="a49f4-196">You can find the names of X509Certificate stores for the `sourceStorename` and `destinationStorename` parameters by compiling and running the following code.</span></span>  
  
 [!code-csharp[Tools.CertMgr#1](../../../samples/snippets/csharp/VS_Snippets_CLR/tools.certmgr/cs/storenames1.cs#1)]
 [!code-vb[Tools.CertMgr#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/tools.certmgr/vb/storenames1.vb#1)]  
  
 <span data-ttu-id="a49f4-197">有关证书的详细信息，请参阅[使用证书](../../../docs/framework/wcf/feature-details/working-with-certificates.md)。</span><span class="sxs-lookup"><span data-stu-id="a49f4-197">For more information about certificates, see [Working with Certificates](../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="a49f4-198">示例</span><span class="sxs-lookup"><span data-stu-id="a49f4-198">Examples</span></span>  
 <span data-ttu-id="a49f4-199">下面的命令显示一个名为 `my` 且包含详细输出的默认系统存储。</span><span class="sxs-lookup"><span data-stu-id="a49f4-199">The following command displays a default system store called `my` with verbose output.</span></span>  
  
```  
certmgr /v /s my  
```  
  
 <span data-ttu-id="a49f4-200">下面的命令将名为 `myFile.ext` 的文件中的所有证书添加到一个名为 `newFile.ext` 的新文件中。</span><span class="sxs-lookup"><span data-stu-id="a49f4-200">The following command adds all the certificates in a file called `myFile.ext` to a new file called `newFile.ext`.</span></span>  
  
```  
certmgr /add /all /c myFile.ext newFile.ext  
```  
  
 <span data-ttu-id="a49f4-201">下面的命令将名为 `testcert.cer` 的文件中的证书添加到 `my` 系统存储中。</span><span class="sxs-lookup"><span data-stu-id="a49f4-201">The following command adds the certificate in a file named `testcert.cer` to the `my` system store.</span></span>  
  
```  
certmgr /add /c testcert.cer /s my  
```  
  
 <span data-ttu-id="a49f4-202">下面的命令将名为 `TrustedCert.cer` 的文件中的证书添加到根证书存储区内。</span><span class="sxs-lookup"><span data-stu-id="a49f4-202">The following command adds the certificate in a file named `TrustedCert.cer` to the root certificate store.</span></span>  
  
```  
certmgr /c /add TrustedCert.cer /s root  
```  
  
 <span data-ttu-id="a49f4-203">下面的命令将 `myCert` 系统存储中具有公用名 `my` 的证书保存到一个名为 `newCert.cer` 的文件中。</span><span class="sxs-lookup"><span data-stu-id="a49f4-203">The following command saves a certificate with the common name `myCert` in the `my` system store to a file called `newCert.cer`.</span></span>  
  
```  
certmgr /add /c /n myCert /s my newCert.cer  
```  
  
 <span data-ttu-id="a49f4-204">下面的命令删除 `my` 系统存储中的所有 CTL，并将生成的存储保存到一个名为 `newStore.str` 的文件中。</span><span class="sxs-lookup"><span data-stu-id="a49f4-204">The following command deletes all CTLs in the `my` system store and saves the resulting store to a file called `newStore.str`.</span></span>  
  
```  
certmgr /del /all /ctl /s my newStore.str  
```  
  
 <span data-ttu-id="a49f4-205">下面的命令将 `my` 系统存储中的一个证书保存到 `newFile` 文件中。</span><span class="sxs-lookup"><span data-stu-id="a49f4-205">The following command saves a certificate in the `my` system store in the file `newFile`.</span></span> <span data-ttu-id="a49f4-206">系统将提示你输入 `my` 中的要用于放置 `newFile` 的证书编号。</span><span class="sxs-lookup"><span data-stu-id="a49f4-206">You will be prompted to enter the certificate number from `my` to put in `newFile`.</span></span>  
  
```  
certmgr /put /c /s my newFile  
```  
  
## <a name="see-also"></a><span data-ttu-id="a49f4-207">请参阅</span><span class="sxs-lookup"><span data-stu-id="a49f4-207">See also</span></span>
- [<span data-ttu-id="a49f4-208">工具</span><span class="sxs-lookup"><span data-stu-id="a49f4-208">Tools</span></span>](../../../docs/framework/tools/index.md)
- [<span data-ttu-id="a49f4-209">Makecert.exe（证书创建工具）</span><span class="sxs-lookup"><span data-stu-id="a49f4-209">Makecert.exe (Certificate Creation Tool)</span></span>](/windows/desktop/SecCrypto/makecert)
- [<span data-ttu-id="a49f4-210">命令提示</span><span class="sxs-lookup"><span data-stu-id="a49f4-210">Command Prompts</span></span>](../../../docs/framework/tools/developer-command-prompt-for-vs.md)
