---
title: C# 编译器选项
ms.date: 07/20/2015
f1_keywords:
- cs.build.options
helpviewer_keywords:
- compiler options [C#]
- csc.exe
- cl.exe compiler, C# options
- Visual C# compiler
- Visual C#, compiler options
ms.assetid: d3403556-1816-4546-a782-e8223a772e44
ms.openlocfilehash: dab91ddd1f2b9c91560329eeb1c51ca7f6f175bd
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2019
ms.locfileid: "73455246"
---
# <a name="c-compiler-options"></a><span data-ttu-id="84897-102">C# 编译器选项</span><span class="sxs-lookup"><span data-stu-id="84897-102">C# Compiler Options</span></span>

<span data-ttu-id="84897-103">编译器生成可执行 (.exe) 文件、动态链接库 (.dll) 或者代码模块 (.netmodule)。</span><span class="sxs-lookup"><span data-stu-id="84897-103">The compiler produces executable (.exe) files, dynamic-link libraries (.dll), or code modules (.netmodule).</span></span>

<span data-ttu-id="84897-104">每个编译器选项均有两种形式： **-option** 和 **/option**。</span><span class="sxs-lookup"><span data-stu-id="84897-104">Every compiler option is available in two forms: **-option** and **/option**.</span></span> <span data-ttu-id="84897-105">此文档仅介绍 **-option** 形式。</span><span class="sxs-lookup"><span data-stu-id="84897-105">The documentation only shows the **-option** form.</span></span>

<span data-ttu-id="84897-106">在 Visual Studio 中，可在 web.config 文件中设置编译器选项。 </span><span class="sxs-lookup"><span data-stu-id="84897-106">In Visual Studio, you set compiler options in the *web.config* file.</span></span> <span data-ttu-id="84897-107">有关详细信息，请参阅 [\<compiler> 元素](../../../framework/configure-apps/file-schema/compiler/compiler-element.md)。</span><span class="sxs-lookup"><span data-stu-id="84897-107">For more information, see [\<compiler> Element](../../../framework/configure-apps/file-schema/compiler/compiler-element.md).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="84897-108">本节内容</span><span class="sxs-lookup"><span data-stu-id="84897-108">In this section</span></span>

- <span data-ttu-id="84897-109">[使用 csc.exe 的命令行生成](command-line-building-with-csc-exe.md) 有关从命令行生成 Visual C# 应用程序的信息。</span><span class="sxs-lookup"><span data-stu-id="84897-109">[Command-line Building With csc.exe](command-line-building-with-csc-exe.md) Information about building a Visual C# application from the command line.</span></span>

- <span data-ttu-id="84897-110">[如何：为 Visual Studio 命令行设置环境变量](how-to-set-environment-variables-for-the-visual-studio-command-line.md) 提供运行 vsvars32.bat  以启用命令行生成的步骤。</span><span class="sxs-lookup"><span data-stu-id="84897-110">[How to: Set Environment Variables for the Visual Studio Command Line](how-to-set-environment-variables-for-the-visual-studio-command-line.md) Provides steps for running *vsvars32.bat* to enable command-line builds.</span></span>

- <span data-ttu-id="84897-111">[按类别列出的 C# 编译器选项](listed-by-category.md) 编译器选项的分类列表。</span><span class="sxs-lookup"><span data-stu-id="84897-111">[C# Compiler Options Listed by Category](listed-by-category.md) A categorical listing of the compiler options.</span></span>

- <span data-ttu-id="84897-112">[按字母顺序列出的 C# 编译器选项](listed-alphabetically.md) 编译器选项按字母顺序列出的列表。</span><span class="sxs-lookup"><span data-stu-id="84897-112">[C# Compiler Options Listed Alphabetically](listed-alphabetically.md) An alphabetical listing of the compiler options.</span></span>

## <a name="related-sections"></a><span data-ttu-id="84897-113">相关章节</span><span class="sxs-lookup"><span data-stu-id="84897-113">Related sections</span></span>

- <span data-ttu-id="84897-114">[生成页，项目设计器](/visualstudio/ide/reference/build-page-project-designer-csharp) 介绍了如何设置属性来控制项目的编译、生成和调试方式。</span><span class="sxs-lookup"><span data-stu-id="84897-114">[Build Page, Project Designer](/visualstudio/ide/reference/build-page-project-designer-csharp) Setting properties that govern how your project is compiled, built, and debugged.</span></span> <span data-ttu-id="84897-115">介绍了 Visual C# 项目的自定义生成步骤。</span><span class="sxs-lookup"><span data-stu-id="84897-115">Includes information about custom build steps in Visual C# projects.</span></span>

- <span data-ttu-id="84897-116">[默认和自定义生成](/visualstudio/ide/compiling-and-building-in-visual-studio) 有关生成类型和配置的信息。</span><span class="sxs-lookup"><span data-stu-id="84897-116">[Default and Custom Builds](/visualstudio/ide/compiling-and-building-in-visual-studio) Information on build types and configurations.</span></span>

- <span data-ttu-id="84897-117">[准备和管理生成](/visualstudio/ide/building-and-cleaning-projects-and-solutions-in-visual-studio) 介绍了 Visual Studio 开发环境中的生成过程。</span><span class="sxs-lookup"><span data-stu-id="84897-117">[Preparing and Managing Builds](/visualstudio/ide/building-and-cleaning-projects-and-solutions-in-visual-studio) Procedures for building within the Visual Studio development environment.</span></span>
