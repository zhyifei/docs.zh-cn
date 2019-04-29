---
title: 无法发出程序集：<error message>
ms.date: 08/14/2018
f1_keywords:
- vbc30145
- bc30145
helpviewer_keywords:
- BC30145
ms.assetid: 2e7eb2b9-eda6-4bdb-95cc-72c7f0be7528
ms.openlocfilehash: d564f4f4462a691504297d65575956c5f06691ca
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61936274"
---
# <a name="unable-to-emit-assembly-error-message"></a><span data-ttu-id="5bc90-102">无法发出程序集：\<错误消息 ></span><span class="sxs-lookup"><span data-stu-id="5bc90-102">Unable to emit assembly: \<error message></span></span>

<span data-ttu-id="5bc90-103">Visual Basic 编译器调用程序集链接器 (*Al.exe*，也称为 Alink) 生成的程序集具有一个清单和链接器可创建程序集的发出阶段报告错误。</span><span class="sxs-lookup"><span data-stu-id="5bc90-103">The Visual Basic compiler calls the Assembly Linker (*Al.exe*, also known as Alink) to generate an assembly with a manifest, and the linker reports an error in the emission stage of creating the assembly.</span></span>

<span data-ttu-id="5bc90-104">**错误 ID:** BC30145</span><span class="sxs-lookup"><span data-stu-id="5bc90-104">**Error ID:** BC30145</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="5bc90-105">更正此错误</span><span class="sxs-lookup"><span data-stu-id="5bc90-105">To correct this error</span></span>

1. <span data-ttu-id="5bc90-106">检查引用的错误信息并参考主题[Al.exe](../../../framework/tools/al-exe-assembly-linker.md)以获得进一步的解释和建议。</span><span class="sxs-lookup"><span data-stu-id="5bc90-106">Examine the quoted error message and consult the topic [Al.exe](../../../framework/tools/al-exe-assembly-linker.md) for further explanation and advice.</span></span>

2. <span data-ttu-id="5bc90-107">请尝试使用手动签名程序集[Al.exe](../../../framework/tools/al-exe-assembly-linker.md)或[Sn.exe （强名称工具）](../../../framework/tools/sn-exe-strong-name-tool.md)。</span><span class="sxs-lookup"><span data-stu-id="5bc90-107">Try signing the assembly manually, using either the [Al.exe](../../../framework/tools/al-exe-assembly-linker.md) or the [Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md).</span></span>

3. <span data-ttu-id="5bc90-108">如果仍然出现错误，则收集有关该情况的信息并通知 Microsoft 产品支持服务。</span><span class="sxs-lookup"><span data-stu-id="5bc90-108">If the error persists, gather information about the circumstances and notify Microsoft Product Support Services.</span></span>

### <a name="to-sign-the-assembly-manually"></a><span data-ttu-id="5bc90-109">手动对程序集进行签名</span><span class="sxs-lookup"><span data-stu-id="5bc90-109">To sign the assembly manually</span></span>

1. <span data-ttu-id="5bc90-110">使用[Sn.exe （强名称工具）](../../../framework/tools/sn-exe-strong-name-tool.md)) 创建公钥/私钥对文件。</span><span class="sxs-lookup"><span data-stu-id="5bc90-110">Use the [Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md)) to create a public/private key pair file.</span></span>

   <span data-ttu-id="5bc90-111">此文件具有 *.snk*扩展。</span><span class="sxs-lookup"><span data-stu-id="5bc90-111">This file has an *.snk* extension.</span></span>

2. <span data-ttu-id="5bc90-112">从项目中删除生成错误的 COM 引用。</span><span class="sxs-lookup"><span data-stu-id="5bc90-112">Delete the COM reference that is generating the error from your project.</span></span>

3. <span data-ttu-id="5bc90-113">打开[Visual Studio 的开发人员命令提示](../../../framework/tools/developer-command-prompt-for-vs.md)。</span><span class="sxs-lookup"><span data-stu-id="5bc90-113">Open the [Developer Command Prompt for Visual Studio](../../../framework/tools/developer-command-prompt-for-vs.md).</span></span>

   <span data-ttu-id="5bc90-114">在 Windows 10 中，输入**开发人员命令提示**任务栏上的搜索框。</span><span class="sxs-lookup"><span data-stu-id="5bc90-114">In Windows 10, enter **Developer command prompt** into the search box on the task bar.</span></span> <span data-ttu-id="5bc90-115">然后，选择**VS 2017 开发人员命令提示**从结果列表中。</span><span class="sxs-lookup"><span data-stu-id="5bc90-115">Then, select **Developer Command Prompt for VS 2017** from the results list.</span></span>

4. <span data-ttu-id="5bc90-116">将目录更改为你想要放置程序集包装的目录。</span><span class="sxs-lookup"><span data-stu-id="5bc90-116">Change the directory to the directory where you want to place your assembly wrapper.</span></span>

5. <span data-ttu-id="5bc90-117">输入以下命令：</span><span class="sxs-lookup"><span data-stu-id="5bc90-117">Enter the following command:</span></span>

    ```cmd
    tlbimp <path to COM reference file> /out:<output assembly name> /keyfile:<path to .snk file>
    ```

   <span data-ttu-id="5bc90-118">可能输入的实际命令的一个示例是：</span><span class="sxs-lookup"><span data-stu-id="5bc90-118">An example of the actual command you might enter is:</span></span>

    ```cmd
    tlbimp c:\windows\system32\msi.dll /out:Interop.WindowsInstaller.dll /keyfile:"c:\documents and settings\mykey.snk"
    ```

   > [!TIP]
   > <span data-ttu-id="5bc90-119">如果路径或文件名包含空格，请使用双引号引起来。</span><span class="sxs-lookup"><span data-stu-id="5bc90-119">Use double quotation marks if a path or file contains spaces.</span></span>

6. <span data-ttu-id="5bc90-120">在 Visual Studio 中，添加对刚创建的文件的.NET 程序集引用。</span><span class="sxs-lookup"><span data-stu-id="5bc90-120">In Visual Studio, add a .NET Assembly reference to the file you just created.</span></span>

## <a name="see-also"></a><span data-ttu-id="5bc90-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="5bc90-121">See also</span></span>

- [<span data-ttu-id="5bc90-122">Al.exe</span><span class="sxs-lookup"><span data-stu-id="5bc90-122">Al.exe</span></span>](../../../framework/tools/al-exe-assembly-linker.md)
- [<span data-ttu-id="5bc90-123">Sn.exe（强名称工具）</span><span class="sxs-lookup"><span data-stu-id="5bc90-123">Sn.exe (Strong Name Tool)</span></span>](../../../framework/tools/sn-exe-strong-name-tool.md)
- [<span data-ttu-id="5bc90-124">如何：创建公钥/私钥对</span><span class="sxs-lookup"><span data-stu-id="5bc90-124">How to: Create a Public-Private Key Pair</span></span>](../../../framework/app-domains/how-to-create-a-public-private-key-pair.md)
- [<span data-ttu-id="5bc90-125">与我们交流</span><span class="sxs-lookup"><span data-stu-id="5bc90-125">Talk to Us</span></span>](/visualstudio/ide/talk-to-us)