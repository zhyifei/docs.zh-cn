---
title: 本机互操作性 - .NET
description: 了解如何与 .NET 中的本机组件交互。
author: jkoritzinsky
ms.author: jekoritz
ms.date: 01/18/2019
ms.openlocfilehash: 85a22394c8c59f51f462bc0a2ba6a11265682db3
ms.sourcegitcommit: b56d59ad42140d277f2acbd003b74d655fdbc9f1
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2019
ms.locfileid: "54416049"
---
# <a name="native-interoperability"></a><span data-ttu-id="abc4d-103">本机互操作性</span><span class="sxs-lookup"><span data-stu-id="abc4d-103">Native interoperability</span></span>

<span data-ttu-id="abc4d-104">以下文章介绍在 .NET 中实现“本机互操作性”的各种方法。</span><span class="sxs-lookup"><span data-stu-id="abc4d-104">The following articles show the various ways of doing "native interoperability" in .NET.</span></span>

<span data-ttu-id="abc4d-105">调用本机代码的原因有以下几种：</span><span class="sxs-lookup"><span data-stu-id="abc4d-105">There are a few reasons why you'd want to call into native code:</span></span>

* <span data-ttu-id="abc4d-106">操作系统附带的许多 API 并不在托管类库中。</span><span class="sxs-lookup"><span data-stu-id="abc4d-106">Operating systems come with a large volume of APIs that aren't present in the managed class libraries.</span></span> <span data-ttu-id="abc4d-107">该应用场景最好的例子就是对硬件或操作系统管理功能的访问。</span><span class="sxs-lookup"><span data-stu-id="abc4d-107">A prime example for this scenario would be access to hardware or operating system management functions.</span></span>
* <span data-ttu-id="abc4d-108">与其他具有或可生成 C 式 ABI（本机 ABI）的组件通信，如通过 [Java 本机接口 (JNI)](https://docs.oracle.com/javase/8/docs/technotes/guides/jni/) 公开的 Java 代码或可生成本机组件的任何其他托管语言。</span><span class="sxs-lookup"><span data-stu-id="abc4d-108">Communicating with other components that have or can produce C-style ABIs (native ABIs), such as Java code that is exposed via [Java Native Interface (JNI)](https://docs.oracle.com/javase/8/docs/technotes/guides/jni/) or any other managed language that could produce a native component.</span></span>
* <span data-ttu-id="abc4d-109">在 Windows 上，安装的大部分软件（例如 Microsoft Office 套件）会注册 COM 组件，用于代表软件的程序，并使开发人员能够自动化或者使用它们。</span><span class="sxs-lookup"><span data-stu-id="abc4d-109">On Windows, most of the software that gets installed, such as the Microsoft Office suite, registers COM components that represent their programs and allow developers to automate them or use them.</span></span> <span data-ttu-id="abc4d-110">在这种情况下，也需要本机互操作性。</span><span class="sxs-lookup"><span data-stu-id="abc4d-110">This also requires native interoperability.</span></span>

<span data-ttu-id="abc4d-111">前述列表并未包括开发人员想要/偏向于/需要与本机组件交互的所有可能场合与情境。</span><span class="sxs-lookup"><span data-stu-id="abc4d-111">The previous list doesn't cover all of the potential situations and scenarios in which the developer would want/like/need to interface with native components.</span></span> <span data-ttu-id="abc4d-112">例如，.NET 类库使用本机互操作性支持来实现其相当多的 API，如控制台支持和操作、文件系统访问，等等。</span><span class="sxs-lookup"><span data-stu-id="abc4d-112">.NET class library, for instance, uses the native interoperability support to implement a fair number of its APIs, like console support and manipulation, file system access and others.</span></span> <span data-ttu-id="abc4d-113">但务必应知道，在需要的情况下是有其他选择的。</span><span class="sxs-lookup"><span data-stu-id="abc4d-113">However, it's important to note that there's an option if needed.</span></span>

> [!NOTE]
> <span data-ttu-id="abc4d-114">本部分中的大多示例是针对 .NET Core 支持的所有三个平台（Windows、Linux 和 macOS）提供的。</span><span class="sxs-lookup"><span data-stu-id="abc4d-114">Most of the examples in this section will be presented for all three supported platforms for .NET Core (Windows, Linux and macOS).</span></span> <span data-ttu-id="abc4d-115">但是，在某些简短的演示性示例中，只显示了一个使用 Windows 文件名和扩展名（即，库的扩展名“dll”）的例子。</span><span class="sxs-lookup"><span data-stu-id="abc4d-115">However, for some short and illustrative examples, just one sample is shown that uses Windows filenames and extensions (that is, "dll" for libraries).</span></span> <span data-ttu-id="abc4d-116">这并不意味着这些功能不能在 Linux 或 macOS 上使用，只是出于方便而未提到这些平台。</span><span class="sxs-lookup"><span data-stu-id="abc4d-116">This doesn't mean that those features aren't available on Linux or macOS, it was done merely for convenience sake.</span></span>

## <a name="see-also"></a><span data-ttu-id="abc4d-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="abc4d-117">See also</span></span>

- [<span data-ttu-id="abc4d-118">平台调用 (P/Invoke)</span><span class="sxs-lookup"><span data-stu-id="abc4d-118">Platform Invoke (P/Invoke)</span></span>](pinvoke.md)
- [<span data-ttu-id="abc4d-119">类型封送</span><span class="sxs-lookup"><span data-stu-id="abc4d-119">Type marshalling</span></span>](type-marshalling.md)
