---
title: "类型提供程序安全性"
description: "了解如何在 F # 中，包括如何更改类型提供程序的信任设置的类型提供程序安全性。"
keywords: "visual f#, f#, 函数编程"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 9c5a8a1f-5a31-490d-83c0-8beabda75c78
ms.openlocfilehash: c8f03ee90d4dce1d3484a9dfe8951d500d509a2b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="type-provider-security"></a><span data-ttu-id="e83f9-104">类型提供程序安全性</span><span class="sxs-lookup"><span data-stu-id="e83f9-104">Type Provider Security</span></span>

<span data-ttu-id="e83f9-105">类型提供程序是包含程序集 (Dll) 引用的 F # 项目或脚本代码以连接到外部数据源并呈现到 F # 类型环境的此类型信息。</span><span class="sxs-lookup"><span data-stu-id="e83f9-105">Type providers are assemblies (DLLs) referenced by your F# project or script that contain code to connect to external data sources and surface this type information to the F# type environment.</span></span> <span data-ttu-id="e83f9-106">通常情况下，引用的程序集中的代码是仅运行时则在编译，然后执行代码 （或对于脚本，将代码发送至 F # Interactive）。</span><span class="sxs-lookup"><span data-stu-id="e83f9-106">Typically, code in referenced assemblies is only run when you compile and then execute the code (or in the case of a script, send the code to F# Interactive).</span></span> <span data-ttu-id="e83f9-107">但是，类型提供程序程序集将运行在 Visual Studio 中，是仅在编辑器中浏览代码时。</span><span class="sxs-lookup"><span data-stu-id="e83f9-107">However, a type provider assembly will run inside Visual Studio when the code is merely browsed in the editor.</span></span> <span data-ttu-id="e83f9-108">这是因为类型提供程序需要运行将额外信息添加到编辑器中，如快速信息工具提示，IntelliSense 完成，依次类推。</span><span class="sxs-lookup"><span data-stu-id="e83f9-108">This happens because type providers need to run to add extra information to the editor, such as Quick Info tooltips, IntelliSense completions, and so on.</span></span> <span data-ttu-id="e83f9-109">因此，有额外的安全注意事项类型提供程序程序集，因为它们自动运行 Visual Studio 进程内。</span><span class="sxs-lookup"><span data-stu-id="e83f9-109">As a result, there are extra security considerations for type provider assemblies, since they run automatically inside the Visual Studio process.</span></span>


## <a name="security-warning-dialog"></a><span data-ttu-id="e83f9-110">安全警告对话框</span><span class="sxs-lookup"><span data-stu-id="e83f9-110">Security Warning Dialog</span></span>
<span data-ttu-id="e83f9-111">在首次使用特定类型提供程序程序集，Visual Studio 将显示一个安全对话框，警告你类型提供程序即将运行。</span><span class="sxs-lookup"><span data-stu-id="e83f9-111">When using a particular type provider assembly for the first time, Visual Studio displays a security dialog that warns you that the type provider is about to run.</span></span> <span data-ttu-id="e83f9-112">Visual Studio 加载类型提供程序之前，它使你可以决定是否信任此特定的提供程序。</span><span class="sxs-lookup"><span data-stu-id="e83f9-112">Before Visual Studio loads the type provider, it gives you the opportunity to decide if you trust this particular provider.</span></span> <span data-ttu-id="e83f9-113">如果您信任的源类型提供程序，然后选择"我信任此类型提供程序"。</span><span class="sxs-lookup"><span data-stu-id="e83f9-113">If you trust the source of the type provider, then select "I trust this type provider."</span></span> <span data-ttu-id="e83f9-114">如果你不信任的源类型提供程序，然后选择"我不信任此类型提供程序。"</span><span class="sxs-lookup"><span data-stu-id="e83f9-114">If you do not trust the source of the type provider, then select "I do not trust this type provider."</span></span> <span data-ttu-id="e83f9-115">信任提供程序使它能够在 Visual Studio 内运行和提供 IntelliSense 和生成功能。</span><span class="sxs-lookup"><span data-stu-id="e83f9-115">Trusting the provider enables it to run inside Visual Studio and provide IntelliSense and build features.</span></span> <span data-ttu-id="e83f9-116">但如果恶意类型提供程序本身，运行其代码可能会危害你的计算机。</span><span class="sxs-lookup"><span data-stu-id="e83f9-116">But if the type provider itself is malicious, running its code could compromise your machine.</span></span>

<span data-ttu-id="e83f9-117">如果你的项目包含引用类型提供程序选择在对话框中不信任的代码，然后在编译时，编译器将报告错误，该值指示类型提供程序不受信任。</span><span class="sxs-lookup"><span data-stu-id="e83f9-117">If your project contains code that references type providers that you chose in the dialog not to trust, then at compile time, the compiler will report an error that indicates that the type provider is untrusted.</span></span> <span data-ttu-id="e83f9-118">由红色波形曲线指示依赖于不受信任的类型提供程序的任何类型。</span><span class="sxs-lookup"><span data-stu-id="e83f9-118">Any types that are dependent on the untrusted type provider are indicated by red squiggles.</span></span> <span data-ttu-id="e83f9-119">则可以安全地浏览在编辑器中的代码。</span><span class="sxs-lookup"><span data-stu-id="e83f9-119">It is safe to browse the code in the editor.</span></span>

<span data-ttu-id="e83f9-120">如果你决定要更改直接在 Visual Studio 中的信任设置，请执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="e83f9-120">If you decide to change the trust setting directly in Visual Studio, perform the following steps.</span></span>


#### <a name="to-change-the-trust-settings-for-type-providers"></a><span data-ttu-id="e83f9-121">若要更改类型提供程序的信任设置</span><span class="sxs-lookup"><span data-stu-id="e83f9-121">To change the trust settings for type providers</span></span>

1. <span data-ttu-id="e83f9-122">上`Tools`菜单上，选择`Options`，然后展开`F# Tools`节点。</span><span class="sxs-lookup"><span data-stu-id="e83f9-122">On the `Tools` menu, select `Options`, and expand the `F# Tools` node.</span></span>
<br />

2. <span data-ttu-id="e83f9-123">选择`Type Providers`，和在类型提供程序列表中，选择复选框适用于类型提供程序信任，并为那些不信任清除该复选框。</span><span class="sxs-lookup"><span data-stu-id="e83f9-123">Select `Type Providers`, and in the list of type providers, select the check box for type providers you trust, and clear the check box for those you don't trust.</span></span>
<br />


## <a name="see-also"></a><span data-ttu-id="e83f9-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e83f9-124">See Also</span></span>
[<span data-ttu-id="e83f9-125">类型提供程序</span><span class="sxs-lookup"><span data-stu-id="e83f9-125">Type Providers</span></span>](index.md)
