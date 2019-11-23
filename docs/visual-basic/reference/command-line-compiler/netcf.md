---
title: -netcf
ms.date: 03/13/2018
f1_keywords:
- /netcf
- -netcf
helpviewer_keywords:
- -netcf compiler option [Visual Basic]
- netcf compiler option [Visual Basic]
- /netcf compiler option [Visual Basic]
ms.assetid: db7cfa59-c315-401c-a59b-0daf355343d6
ms.openlocfilehash: 3df7e622f97a5a1291736180e3964b1b3deaea2f
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005446"
---
# <a name="-netcf"></a><span data-ttu-id="5aacb-102">-netcf</span><span class="sxs-lookup"><span data-stu-id="5aacb-102">-netcf</span></span>

<span data-ttu-id="5aacb-103">设置编译器以面向 .NET Compact Framework。</span><span class="sxs-lookup"><span data-stu-id="5aacb-103">Sets the compiler to target the .NET Compact Framework.</span></span>

## <a name="syntax"></a><span data-ttu-id="5aacb-104">语法</span><span class="sxs-lookup"><span data-stu-id="5aacb-104">Syntax</span></span>

```console
-netcf
```

## <a name="remarks"></a><span data-ttu-id="5aacb-105">备注</span><span class="sxs-lookup"><span data-stu-id="5aacb-105">Remarks</span></span>

<span data-ttu-id="5aacb-106">`-netcf` 选项导致 Visual Basic 编译器以 .NET Compact Framework 而不是完整 .NET Framework 为目标。</span><span class="sxs-lookup"><span data-stu-id="5aacb-106">The `-netcf` option causes the Visual Basic compiler to target the .NET Compact Framework rather than the full .NET Framework.</span></span> <span data-ttu-id="5aacb-107">仅在完整 .NET Framework 中显示的语言功能处于禁用状态。</span><span class="sxs-lookup"><span data-stu-id="5aacb-107">Language functionality that is present only in the full .NET Framework is disabled.</span></span>

<span data-ttu-id="5aacb-108">`-netcf` 选项设计为与[-sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md)一起使用。</span><span class="sxs-lookup"><span data-stu-id="5aacb-108">The `-netcf` option is designed to be used with [-sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md).</span></span> <span data-ttu-id="5aacb-109">`-netcf` 禁用的语言功能与 `-sdkpath`面向的文件中不存在相同的语言功能。</span><span class="sxs-lookup"><span data-stu-id="5aacb-109">The language features disabled by `-netcf` are the same language features not present in the files targeted with `-sdkpath`.</span></span>

> [!NOTE]
> <span data-ttu-id="5aacb-110">`-netcf` 选项在 Visual Studio 开发环境中不可用;仅当从命令行进行编译时，它才可用。</span><span class="sxs-lookup"><span data-stu-id="5aacb-110">The `-netcf` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span> <span data-ttu-id="5aacb-111">`-netcf` 选项是在加载 Visual Basic 设备项目时设置的。</span><span class="sxs-lookup"><span data-stu-id="5aacb-111">The `-netcf` option is set when a Visual Basic device project is loaded.</span></span>

<span data-ttu-id="5aacb-112">`-netcf` 选项更改以下语言功能：</span><span class="sxs-lookup"><span data-stu-id="5aacb-112">The `-netcf` option changes the following language features:</span></span>

- <span data-ttu-id="5aacb-113">禁用了[End \<关键字 > 语句](../../../visual-basic/language-reference/statements/end-keyword-statement.md)关键字，该关键字终止程序的执行。</span><span class="sxs-lookup"><span data-stu-id="5aacb-113">The [End \<keyword> Statement](../../../visual-basic/language-reference/statements/end-keyword-statement.md) keyword, which terminates execution of a program, is disabled.</span></span> <span data-ttu-id="5aacb-114">下面的程序在编译和运行时不 `-netcf`，但在编译时与 `-netcf`发生了故障。</span><span class="sxs-lookup"><span data-stu-id="5aacb-114">The following program compiles and runs without `-netcf` but fails at compile time with `-netcf`.</span></span>

  [!code-vb[VbVbalrCompiler#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/netcf.vb#34)]

- <span data-ttu-id="5aacb-115">所有窗体中的后期绑定都处于禁用状态。</span><span class="sxs-lookup"><span data-stu-id="5aacb-115">Late binding, in all forms, is disabled.</span></span> <span data-ttu-id="5aacb-116">如果遇到可识别的后期绑定方案，则会生成编译时错误。</span><span class="sxs-lookup"><span data-stu-id="5aacb-116">Compile-time errors are generated when recognized late-binding scenarios are encountered.</span></span> <span data-ttu-id="5aacb-117">下面的程序在编译和运行时不 `-netcf`，但在编译时与 `-netcf`发生了故障。</span><span class="sxs-lookup"><span data-stu-id="5aacb-117">The following program compiles and runs without `-netcf` but fails at compile time with `-netcf`.</span></span>

  [!code-vb[VbVbalrCompiler#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#35)]

- <span data-ttu-id="5aacb-118">[Auto](../../../visual-basic/language-reference/modifiers/auto.md)、 [Ansi](../../../visual-basic/language-reference/modifiers/ansi.md)和[Unicode](../../../visual-basic/language-reference/modifiers/unicode.md)修饰符已禁用。</span><span class="sxs-lookup"><span data-stu-id="5aacb-118">The [Auto](../../../visual-basic/language-reference/modifiers/auto.md), [Ansi](../../../visual-basic/language-reference/modifiers/ansi.md), and [Unicode](../../../visual-basic/language-reference/modifiers/unicode.md) modifiers are disabled.</span></span> <span data-ttu-id="5aacb-119">[Declare 语句](../../../visual-basic/language-reference/statements/declare-statement.md)语句的语法还会修改为 `Declare Sub|Function name Lib "library" [Alias "alias"] [([arglist])]`。</span><span class="sxs-lookup"><span data-stu-id="5aacb-119">The syntax of the [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) statement is also modified to `Declare Sub|Function name Lib "library" [Alias "alias"] [([arglist])]`.</span></span> <span data-ttu-id="5aacb-120">下面的代码演示了对编译 `-netcf` 的影响。</span><span class="sxs-lookup"><span data-stu-id="5aacb-120">The following code shows the effect of `-netcf` on a compilation.</span></span>

  [!code-vb[VbVbalrCompiler#36](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#36)]

- <span data-ttu-id="5aacb-121">使用从 Visual Basic 中删除的 Visual Basic 6.0 关键字会在使用 `-netcf` 时生成不同的错误。</span><span class="sxs-lookup"><span data-stu-id="5aacb-121">Using Visual Basic 6.0 keywords that were removed from Visual Basic generates a different error when `-netcf` is used.</span></span> <span data-ttu-id="5aacb-122">这会影响以下关键字的错误消息：</span><span class="sxs-lookup"><span data-stu-id="5aacb-122">This affects the error messages for the following keywords:</span></span>

  - `Open`

  - `Close`

  - `Put`

  - `Print`

  - `Write`

  - `Input`

  - `Lock`

  - `Unlock`

  - `Seek`

  - `Width`

  - `Name`

  - `FreeFile`

  - `EOF`

  - `Loc`

  - `LOF`

  - `Line`

## <a name="example"></a><span data-ttu-id="5aacb-123">示例</span><span class="sxs-lookup"><span data-stu-id="5aacb-123">Example</span></span>

<span data-ttu-id="5aacb-124">下面的代码使用 C 驱动器上 .NET Compact Framework 的默认安装目录中的 mscorlib.dll 和 .NET Compact Framework 版本，将 `Myfile.vb` 编译为。</span><span class="sxs-lookup"><span data-stu-id="5aacb-124">The following code compiles `Myfile.vb` with the .NET Compact Framework, using the versions of mscorlib.dll and Microsoft.VisualBasic.dll found in the default installation directory of the .NET Compact Framework on the C drive.</span></span> <span data-ttu-id="5aacb-125">通常，您将使用最新版本的 .NET Compact Framework。</span><span class="sxs-lookup"><span data-stu-id="5aacb-125">Typically, you would use the most recent version of the .NET Compact Framework.</span></span>

```console
vbc -netcf -sdkpath:"c:\Program Files\Microsoft Visual Studio .NET 2003\CompactFrameworkSDK\v1.0.5000\Windows CE " myfile.vb
```

## <a name="see-also"></a><span data-ttu-id="5aacb-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5aacb-126">See also</span></span>

- [<span data-ttu-id="5aacb-127">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="5aacb-127">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="5aacb-128">示例编译命令行</span><span class="sxs-lookup"><span data-stu-id="5aacb-128">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="5aacb-129">-sdkpath</span><span class="sxs-lookup"><span data-stu-id="5aacb-129">-sdkpath</span></span>](../../../visual-basic/reference/command-line-compiler/sdkpath.md)
