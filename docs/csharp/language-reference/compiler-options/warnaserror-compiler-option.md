---
title: -warnaserror（C# 编译器选项）
ms.date: 07/20/2015
f1_keywords:
- /warnaserror
helpviewer_keywords:
- /warnaserror compiler option [C#]
- -warnaserror compiler option [C#]
- warnaserror compiler option [C#]
ms.assetid: 04680ec3-08d6-4e2e-a274-38310e10e33c
ms.openlocfilehash: 66c78ee56c9d5153b5b878b2e695ad4ee6bffe0b
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/19/2019
ms.locfileid: "69606249"
---
# <a name="-warnaserror-c-compiler-options"></a><span data-ttu-id="5343a-102">-warnaserror（C# 编译器选项）</span><span class="sxs-lookup"><span data-stu-id="5343a-102">-warnaserror (C# Compiler Options)</span></span>
<span data-ttu-id="5343a-103">-warnaserror+ 选项将所有警告视为错误 </span><span class="sxs-lookup"><span data-stu-id="5343a-103">The **-warnaserror+** option treats all warnings as errors</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5343a-104">语法</span><span class="sxs-lookup"><span data-stu-id="5343a-104">Syntax</span></span>  
  
```console  
-warnaserror[+ | -][:warning-list]  
```  
  
## <a name="remarks"></a><span data-ttu-id="5343a-105">备注</span><span class="sxs-lookup"><span data-stu-id="5343a-105">Remarks</span></span>  
 <span data-ttu-id="5343a-106">通常报告为警告的消息被报告为错误，生成过程暂停（不生成任何输出文件）。</span><span class="sxs-lookup"><span data-stu-id="5343a-106">Any messages that would ordinarily be reported as warnings are instead reported as errors, and the build process is halted (no output files are built).</span></span>  
  
 <span data-ttu-id="5343a-107">默认情况下，-warnaserror- 将生效，导致警告不会阻止生成输出文件  。</span><span class="sxs-lookup"><span data-stu-id="5343a-107">By default, **-warnaserror-** is in effect, which causes warnings to not prevent the generation of an output file.</span></span> <span data-ttu-id="5343a-108">-warnaserror 与 -warnaserror+ 相同，会导致将警告视为错误   。</span><span class="sxs-lookup"><span data-stu-id="5343a-108">**-warnaserror**, which is the same as **-warnaserror+**, causes warnings to be treated as errors.</span></span>  
  
 <span data-ttu-id="5343a-109">（可选）如果希望仅将一些特定警告视为错误，则可以指定视为错误的警告编号的逗号分隔列表。</span><span class="sxs-lookup"><span data-stu-id="5343a-109">Optionally, if you want only a few specific warnings to be treated as errors, you may specify a comma-separated list of warning numbers to treat as errors.</span></span>  
  
 <span data-ttu-id="5343a-110">使用 [-warn](./warn-compiler-option.md) 指定想要编译器显示的警告等级。</span><span class="sxs-lookup"><span data-stu-id="5343a-110">Use [-warn](./warn-compiler-option.md) to specify the level of warnings that you want the compiler to display.</span></span> <span data-ttu-id="5343a-111">使用 [-nowarn](./nowarn-compiler-option.md) 禁用某些警告。</span><span class="sxs-lookup"><span data-stu-id="5343a-111">Use [-nowarn](./nowarn-compiler-option.md) to disable certain warnings.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="5343a-112">在 Visual Studio 开发环境中设置此编译器选项</span><span class="sxs-lookup"><span data-stu-id="5343a-112">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="5343a-113">打开项目的“属性”  页。</span><span class="sxs-lookup"><span data-stu-id="5343a-113">Open the project's **Properties** page.</span></span>  
  
2. <span data-ttu-id="5343a-114">单击“生成”  属性页。</span><span class="sxs-lookup"><span data-stu-id="5343a-114">Click the **Build** property page.</span></span>  
  
3. <span data-ttu-id="5343a-115">修改“将警告视为错误”  属性。</span><span class="sxs-lookup"><span data-stu-id="5343a-115">Modify the **Treat Warnings As Errors** property.</span></span>  
  
 <span data-ttu-id="5343a-116">若要以编程方式设置此编译器选项，请参阅 <xref:VSLangProj80.CSharpProjectConfigurationProperties3.TreatWarningsAsErrors>。</span><span class="sxs-lookup"><span data-stu-id="5343a-116">To set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.TreatWarningsAsErrors>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5343a-117">示例</span><span class="sxs-lookup"><span data-stu-id="5343a-117">Example</span></span>  
 <span data-ttu-id="5343a-118">编译 `in.cs` 并使编译器不显示警告：</span><span class="sxs-lookup"><span data-stu-id="5343a-118">Compile `in.cs` and have the compiler display no warnings:</span></span>  
  
```console  
csc -warnaserror in.cs  
csc -warnaserror:642,649,652 in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="5343a-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="5343a-119">See also</span></span>

- [<span data-ttu-id="5343a-120">C# 编译器选项</span><span class="sxs-lookup"><span data-stu-id="5343a-120">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="5343a-121">管理项目和解决方案属性</span><span class="sxs-lookup"><span data-stu-id="5343a-121">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
