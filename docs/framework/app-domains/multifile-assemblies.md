---
title: 多文件程序集
ms.date: 03/30/2017
helpviewer_keywords:
- assemblies [.NET Framework], multifile
- entry point for assembly
- compiling assemblies
- command-line compilers
- assembly manifest, multifile assemblies
- code modules
- multifile assemblies
ms.assetid: 13509e73-db77-4645-8165-aad8dfaedff6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bad63bbc8e221f306e5807f51fbbb8eb4761d0fb
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54599174"
---
# <a name="multifile-assemblies"></a><span data-ttu-id="63838-102">多文件程序集</span><span class="sxs-lookup"><span data-stu-id="63838-102">Multifile Assemblies</span></span>

<span data-ttu-id="63838-103">可以使用命令行编译器或 Visual Studio 和 Visual C++，创建多文件程序集。</span><span class="sxs-lookup"><span data-stu-id="63838-103">You can create multifile assemblies using command-line compilers or Visual Studio with Visual C++.</span></span> <span data-ttu-id="63838-104">程序集中的一个文件必须包含程序集清单。</span><span class="sxs-lookup"><span data-stu-id="63838-104">One file in the assembly must contain the assembly manifest.</span></span> <span data-ttu-id="63838-105">启动应用程序的程序集还必须包含入口点，如 Main 或 WinMain 方法。</span><span class="sxs-lookup"><span data-stu-id="63838-105">An assembly that starts an application must also contain an entry point, such as a Main or WinMain method.</span></span>

<span data-ttu-id="63838-106">例如，假设应用程序包含两个代码模块：Client.cs 和 Stringer.cs。</span><span class="sxs-lookup"><span data-stu-id="63838-106">For example, suppose you have an application that contains two code modules, Client.cs and Stringer.cs.</span></span> <span data-ttu-id="63838-107">Stringer.cs 创建由 Client.cs 中的代码引用的 `myStringer` 命名空间。</span><span class="sxs-lookup"><span data-stu-id="63838-107">Stringer.cs creates the `myStringer` namespace that is referenced by the code in Client.cs.</span></span> <span data-ttu-id="63838-108">Client.cs 包含作为应用程序入口点的 `Main` 方法。</span><span class="sxs-lookup"><span data-stu-id="63838-108">Client.cs contains the `Main` method, which is the application's entry point.</span></span> <span data-ttu-id="63838-109">在此示例中，编译两个代码模块，然后创建一个包含程序集清单的第三个文件，用于启动应用程序。</span><span class="sxs-lookup"><span data-stu-id="63838-109">In this example, you compile the two code modules, and then create a third file that contains the assembly manifest, which launches the application.</span></span> <span data-ttu-id="63838-110">程序集清单将同时引用 `Client` 和 `Stringer` 模块。</span><span class="sxs-lookup"><span data-stu-id="63838-110">The assembly manifest references both the `Client` and `Stringer` modules.</span></span>

> [!NOTE]
> <span data-ttu-id="63838-111">多文件程序集只能有一个入口点，即使该程序集具有多个代码模块。</span><span class="sxs-lookup"><span data-stu-id="63838-111">Multifile assemblies can have only one entry point, even if the assembly has multiple code modules.</span></span>

<span data-ttu-id="63838-112">创建多文件程序集的原因有以下几个：</span><span class="sxs-lookup"><span data-stu-id="63838-112">There are several reasons you might want to create a multifile assembly:</span></span>

-   <span data-ttu-id="63838-113">合并用不同语言编写的模块。</span><span class="sxs-lookup"><span data-stu-id="63838-113">To combine modules written in different languages.</span></span> <span data-ttu-id="63838-114">这是创建多文件程序集最常见的原因。</span><span class="sxs-lookup"><span data-stu-id="63838-114">This is the most common reason for creating a multifile assembly.</span></span>

-   <span data-ttu-id="63838-115">将不常用的类型放在只在需要时才下载的模块中，以优化应用程序的下载。</span><span class="sxs-lookup"><span data-stu-id="63838-115">To optimize downloading an application by putting seldom-used types in a module that is downloaded only when needed.</span></span>

    > [!NOTE]
    > <span data-ttu-id="63838-116">如果要创建将使用 `<object>` 标记和 Microsoft Internet Explorer 来下载的应用程序，创建多文件程序集就很重要。</span><span class="sxs-lookup"><span data-stu-id="63838-116">If you are creating applications that will be downloaded using the `<object>` tag with Microsoft Internet Explorer, it is important that you create multifile assemblies.</span></span> <span data-ttu-id="63838-117">在此方案中，创建与只包含程序集清单的代码模块分开的文件。</span><span class="sxs-lookup"><span data-stu-id="63838-117">In this scenario, you create a file separate from your code modules that contains only the assembly manifest.</span></span> <span data-ttu-id="63838-118">Internet Explorer 首先下载程序集清单，然后创建辅助线程以下载所需的任何其他模块或程序集。</span><span class="sxs-lookup"><span data-stu-id="63838-118">Internet Explorer downloads the assembly manifest first, and then creates worker threads to download any additional modules or assemblies required.</span></span> <span data-ttu-id="63838-119">由于正在下载包含程序集清单的文件，Internet Explorer 将不响应用户的输入。</span><span class="sxs-lookup"><span data-stu-id="63838-119">While the file containing the assembly manifest is being downloaded, Internet Explorer will be unresponsive to user input.</span></span> <span data-ttu-id="63838-120">包含程序集清单的文件越小，Internet Explorer 不作响应的时间就越短。</span><span class="sxs-lookup"><span data-stu-id="63838-120">The smaller the file containing the assembly manifest, the less time Internet Explorer will be unresponsive.</span></span>

-   <span data-ttu-id="63838-121">合并由多个开发人员编写的代码模块。</span><span class="sxs-lookup"><span data-stu-id="63838-121">To combine code modules written by several developers.</span></span> <span data-ttu-id="63838-122">虽然每一位开发人员都可以将各个代码模块编译成程序集，但这样会强制一些类型公开（如果所有模块均放在多文件程序集中，则不会公开）。</span><span class="sxs-lookup"><span data-stu-id="63838-122">Although each developer can compile each code module into an assembly, this can force some types to be exposed publicly that are not exposed if all modules are put into a multifile assembly.</span></span>

<span data-ttu-id="63838-123">创建程序集后，可为包含程序集清单（并因此包含程序集）的文件签名，或者为文件（及程序集）指定强名称并将其放在全局程序集缓存中。</span><span class="sxs-lookup"><span data-stu-id="63838-123">Once you create the assembly, you can sign the file that contains the assembly manifest (and hence the assembly), or you can give the file (and the assembly) a strong name and put it in the global assembly cache.</span></span>

## <a name="see-also"></a><span data-ttu-id="63838-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="63838-124">See also</span></span>

- [<span data-ttu-id="63838-125">如何：生成单文件程序集</span><span class="sxs-lookup"><span data-stu-id="63838-125">How to: Build a Multifile Assembly</span></span>](../../../docs/framework/app-domains/how-to-build-a-multifile-assembly.md)
- [<span data-ttu-id="63838-126">使用程序集编程</span><span class="sxs-lookup"><span data-stu-id="63838-126">Programming with Assemblies</span></span>](../../../docs/framework/app-domains/programming-with-assemblies.md)