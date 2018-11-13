---
title: 入口点 (F#)
description: 了解如何设置入口点为 F# 程序编译为可执行文件，正式开始执行的位置。
ms.date: 05/16/2016
ms.openlocfilehash: 298500931d49c891a7a243295333df3a9f5d413e
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "45698370"
---
# <a name="entry-point"></a><span data-ttu-id="2e9b5-103">入口点</span><span class="sxs-lookup"><span data-stu-id="2e9b5-103">Entry Point</span></span>

<span data-ttu-id="2e9b5-104">本主题介绍用于将入口点设置为 F# 程序的方法。</span><span class="sxs-lookup"><span data-stu-id="2e9b5-104">This topic describes the method that you use to set the entry point to an F# program.</span></span>

## <a name="syntax"></a><span data-ttu-id="2e9b5-105">语法</span><span class="sxs-lookup"><span data-stu-id="2e9b5-105">Syntax</span></span>

```fsharp
[<EntryPoint>]
let-function-binding
```

## <a name="remarks"></a><span data-ttu-id="2e9b5-106">备注</span><span class="sxs-lookup"><span data-stu-id="2e9b5-106">Remarks</span></span>

<span data-ttu-id="2e9b5-107">在上述语法中， *let 函数绑定*是中的函数的定义`let`绑定。</span><span class="sxs-lookup"><span data-stu-id="2e9b5-107">In the previous syntax, *let-function-binding* is the definition of a function in a `let` binding.</span></span>

<span data-ttu-id="2e9b5-108">可执行文件正式开始执行时编译的程序入口点。</span><span class="sxs-lookup"><span data-stu-id="2e9b5-108">The entry point to a program that is compiled as an executable file is where execution formally starts.</span></span> <span data-ttu-id="2e9b5-109">您可以通过应用指定的 F# 应用程序的入口点`EntryPoint`属性为该程序的`main`函数。</span><span class="sxs-lookup"><span data-stu-id="2e9b5-109">You specify the entry point to an F# application by applying the `EntryPoint` attribute to the program's `main` function.</span></span> <span data-ttu-id="2e9b5-110">此函数 (使用创建的`let`绑定) 必须是最后一个已编译文件中的最后一个函数。</span><span class="sxs-lookup"><span data-stu-id="2e9b5-110">This function (created by using a `let` binding) must be the last function in the last compiled file.</span></span> <span data-ttu-id="2e9b5-111">最后一个已编译的文件是项目中的最后一个文件或传递给命令行的最后一个文件。</span><span class="sxs-lookup"><span data-stu-id="2e9b5-111">The last compiled file is the last file in the project or the last file that is passed to the command line.</span></span>

<span data-ttu-id="2e9b5-112">入口点函数具有类型`string array -> int`。</span><span class="sxs-lookup"><span data-stu-id="2e9b5-112">The entry point function has type `string array -> int`.</span></span> <span data-ttu-id="2e9b5-113">在命令行上提供的参数传递给`main`字符串数组中的函数。</span><span class="sxs-lookup"><span data-stu-id="2e9b5-113">The arguments provided on the command line are passed to the `main` function in the array of strings.</span></span> <span data-ttu-id="2e9b5-114">数组的第一个元素是第一个参数;可执行文件的名称不包含在数组中，因为它是其他一些语言中。</span><span class="sxs-lookup"><span data-stu-id="2e9b5-114">The first element of the array is the first argument; the name of the executable file is not included in the array, as it is in some other languages.</span></span> <span data-ttu-id="2e9b5-115">返回的值用作进程退出代码。</span><span class="sxs-lookup"><span data-stu-id="2e9b5-115">The return value is used as the exit code for the process.</span></span> <span data-ttu-id="2e9b5-116">零通常指示成功;非零值指示错误。</span><span class="sxs-lookup"><span data-stu-id="2e9b5-116">Zero usually indicates success; nonzero values indicate an error.</span></span> <span data-ttu-id="2e9b5-117">特定含义的非零返回代码; 没有约定返回代码的含义是特定于应用程序。</span><span class="sxs-lookup"><span data-stu-id="2e9b5-117">There is no convention for the specific meaning of nonzero return codes; the meanings of the return codes are application-specific.</span></span>

<span data-ttu-id="2e9b5-118">下面的示例演示一个简单`main`函数。</span><span class="sxs-lookup"><span data-stu-id="2e9b5-118">The following example illustrates a simple `main` function.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/entry-point/snippet501.fs)]

<span data-ttu-id="2e9b5-119">使用命令行执行此代码时`EntryPoint.exe 1 2 3`，输出如下所示。</span><span class="sxs-lookup"><span data-stu-id="2e9b5-119">When this code is executed with the command line `EntryPoint.exe 1 2 3`, the output is as follows.</span></span>

```console
Arguments passed to function : [|"1"; "2"; "3"|]
```

## <a name="implicit-entry-point"></a><span data-ttu-id="2e9b5-120">隐式入口点</span><span class="sxs-lookup"><span data-stu-id="2e9b5-120">Implicit Entry Point</span></span>

<span data-ttu-id="2e9b5-121">程序没有**入口点**显式指示的入口点，最后一个文件中的最高级别绑定，要编译的属性用作入口点。</span><span class="sxs-lookup"><span data-stu-id="2e9b5-121">When a program has no **EntryPoint** attribute that explicitly indicates the entry point, the top level bindings in the last file to be compiled are used as the entry point.</span></span>

## <a name="see-also"></a><span data-ttu-id="2e9b5-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="2e9b5-122">See also</span></span>

- [<span data-ttu-id="2e9b5-123">函数</span><span class="sxs-lookup"><span data-stu-id="2e9b5-123">Functions</span></span>](index.md)
- [<span data-ttu-id="2e9b5-124">let 绑定</span><span class="sxs-lookup"><span data-stu-id="2e9b5-124">let Bindings</span></span>](let-bindings.md)
