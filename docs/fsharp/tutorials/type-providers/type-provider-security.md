---
title: 类型提供程序安全性
description: 了解如何在类型提供程序安全性F#，包括如何更改的类型提供程序的信任设置。
ms.date: 05/16/2016
ms.openlocfilehash: 9ccb33d7298736c3d6b54980b6fe09bc9f2e0259
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/19/2018
ms.locfileid: "53611186"
---
# <a name="type-provider-security"></a><span data-ttu-id="3733f-103">类型提供程序安全性</span><span class="sxs-lookup"><span data-stu-id="3733f-103">Type Provider Security</span></span>

<span data-ttu-id="3733f-104">类型提供程序将所引用的程序集 (Dll) 在F#项目或脚本包含代码以连接到外部数据源并呈现到此类型信息的F#类型的环境。</span><span class="sxs-lookup"><span data-stu-id="3733f-104">Type providers are assemblies (DLLs) referenced by your F# project or script that contain code to connect to external data sources and surface this type information to the F# type environment.</span></span> <span data-ttu-id="3733f-105">通常情况下，代码中引用的程序集只运行时编译，并执行代码 (或在脚本的情况下发送到的代码F#交互)。</span><span class="sxs-lookup"><span data-stu-id="3733f-105">Typically, code in referenced assemblies is only run when you compile and then execute the code (or in the case of a script, send the code to F# Interactive).</span></span> <span data-ttu-id="3733f-106">但是，将在 Visual Studio 运行类型提供程序程序集，只是在编辑器中浏览代码时多。</span><span class="sxs-lookup"><span data-stu-id="3733f-106">However, a type provider assembly will run inside Visual Studio when the code is merely browsed in the editor.</span></span> <span data-ttu-id="3733f-107">这是因为类型提供程序需要运行到编辑器，例如快速信息工具提示，IntelliSense 完成添加额外信息等。</span><span class="sxs-lookup"><span data-stu-id="3733f-107">This happens because type providers need to run to add extra information to the editor, such as Quick Info tooltips, IntelliSense completions, and so on.</span></span> <span data-ttu-id="3733f-108">因此，有一些额外的安全注意事项类型提供程序程序集，因为它们在 Visual Studio 进程内自动运行。</span><span class="sxs-lookup"><span data-stu-id="3733f-108">As a result, there are extra security considerations for type provider assemblies, since they run automatically inside the Visual Studio process.</span></span>

## <a name="security-warning-dialog"></a><span data-ttu-id="3733f-109">安全警告对话框</span><span class="sxs-lookup"><span data-stu-id="3733f-109">Security Warning Dialog</span></span>

<span data-ttu-id="3733f-110">当首次使用特定类型提供程序程序集，Visual Studio 将显示一个安全对话框，警告类型提供程序即将运行。</span><span class="sxs-lookup"><span data-stu-id="3733f-110">When using a particular type provider assembly for the first time, Visual Studio displays a security dialog that warns you that the type provider is about to run.</span></span> <span data-ttu-id="3733f-111">Visual Studio 将加载的类型提供程序之前，它使你能够决定是否信任此特定的提供程序。</span><span class="sxs-lookup"><span data-stu-id="3733f-111">Before Visual Studio loads the type provider, it gives you the opportunity to decide if you trust this particular provider.</span></span> <span data-ttu-id="3733f-112">如果您信任的源类型提供程序，然后选择"我信任此类型提供程序"。</span><span class="sxs-lookup"><span data-stu-id="3733f-112">If you trust the source of the type provider, then select "I trust this type provider."</span></span> <span data-ttu-id="3733f-113">如果不信任的源类型提供程序，然后选择"我不信任此类型提供程序"。</span><span class="sxs-lookup"><span data-stu-id="3733f-113">If you do not trust the source of the type provider, then select "I do not trust this type provider."</span></span> <span data-ttu-id="3733f-114">信任提供程序使其能够在 Visual Studio 运行和提供智能感知和生成功能。</span><span class="sxs-lookup"><span data-stu-id="3733f-114">Trusting the provider enables it to run inside Visual Studio and provide IntelliSense and build features.</span></span> <span data-ttu-id="3733f-115">但是，如果恶意类型提供程序本身，运行其代码可能会泄露你的计算机。</span><span class="sxs-lookup"><span data-stu-id="3733f-115">But if the type provider itself is malicious, running its code could compromise your machine.</span></span>

<span data-ttu-id="3733f-116">如果你的项目包含引用类型提供程序选择对话框中不信任的代码，然后在编译时，编译器将报告一个错误，指示类型提供程序不受信任。</span><span class="sxs-lookup"><span data-stu-id="3733f-116">If your project contains code that references type providers that you chose in the dialog not to trust, then at compile time, the compiler will report an error that indicates that the type provider is untrusted.</span></span> <span data-ttu-id="3733f-117">由红色波形曲线指示依赖于不受信任的类型提供程序的任何类型。</span><span class="sxs-lookup"><span data-stu-id="3733f-117">Any types that are dependent on the untrusted type provider are indicated by red squiggles.</span></span> <span data-ttu-id="3733f-118">它可以安全地浏览在编辑器中的代码。</span><span class="sxs-lookup"><span data-stu-id="3733f-118">It is safe to browse the code in the editor.</span></span>

<span data-ttu-id="3733f-119">如果您决定更改的信任设置，直接在 Visual Studio 中，执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="3733f-119">If you decide to change the trust setting directly in Visual Studio, perform the following steps.</span></span>

### <a name="to-change-the-trust-settings-for-type-providers"></a><span data-ttu-id="3733f-120">若要更改类型提供程序的信任设置</span><span class="sxs-lookup"><span data-stu-id="3733f-120">To change the trust settings for type providers</span></span>

1. <span data-ttu-id="3733f-121">上`Tools`菜单中，选择`Options`，然后展开`F# Tools`节点。</span><span class="sxs-lookup"><span data-stu-id="3733f-121">On the `Tools` menu, select `Options`, and expand the `F# Tools` node.</span></span>

2. <span data-ttu-id="3733f-122">选择`Type Providers`，和在类型提供程序列表中，类型提供程序信任，请选中复选框并清除该复选框，对于那些不信任。</span><span class="sxs-lookup"><span data-stu-id="3733f-122">Select `Type Providers`, and in the list of type providers, select the check box for type providers you trust, and clear the check box for those you don't trust.</span></span>

## <a name="see-also"></a><span data-ttu-id="3733f-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="3733f-123">See also</span></span>

- [<span data-ttu-id="3733f-124">类型提供程序</span><span class="sxs-lookup"><span data-stu-id="3733f-124">Type Providers</span></span>](index.md)