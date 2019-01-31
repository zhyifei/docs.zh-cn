---
title: -warn（C# 编译器选项）
ms.date: 07/20/2015
f1_keywords:
- /warn
helpviewer_keywords:
- warning level [C#]
- /w compiler option [C#]
- -w compiler option [C#]
- -warn compiler option [C#]
- /warn compiler option [C#]
- w compiler option [C#]
- warn compiler option [C#]
ms.assetid: 5f80ff59-4991-4382-9f9a-77da18446e71
ms.openlocfilehash: 5a4ecd1fbe5bb79a67d9df07d8f1a93830b03880
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54499864"
---
# <a name="-warn-c-compiler-options"></a><span data-ttu-id="ebdfb-102">-warn（C# 编译器选项）</span><span class="sxs-lookup"><span data-stu-id="ebdfb-102">-warn (C# Compiler Options)</span></span>
<span data-ttu-id="ebdfb-103">-warn 选项指定编译器显示的警告等级。</span><span class="sxs-lookup"><span data-stu-id="ebdfb-103">The **-warn** option specifies the warning level for the compiler to display.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ebdfb-104">语法</span><span class="sxs-lookup"><span data-stu-id="ebdfb-104">Syntax</span></span>  
  
```console  
-warn:option  
```  
  
## <a name="arguments"></a><span data-ttu-id="ebdfb-105">自变量</span><span class="sxs-lookup"><span data-stu-id="ebdfb-105">Arguments</span></span>  
 `option`  
 <span data-ttu-id="ebdfb-106">要为编译显示的警告等级：较低的数字仅显示高严重性警告；较高的数字显示更多警告。</span><span class="sxs-lookup"><span data-stu-id="ebdfb-106">The warning level you want displayed for the compilation: Lower numbers show only high severity warnings; higher numbers show more warnings.</span></span> <span data-ttu-id="ebdfb-107">有效值为 0-4：</span><span class="sxs-lookup"><span data-stu-id="ebdfb-107">Valid values are 0-4:</span></span>  
  
|<span data-ttu-id="ebdfb-108">警告级别</span><span class="sxs-lookup"><span data-stu-id="ebdfb-108">Warning level</span></span>|<span data-ttu-id="ebdfb-109">含义</span><span class="sxs-lookup"><span data-stu-id="ebdfb-109">Meaning</span></span>|  
|-------------------|-------------|  
|<span data-ttu-id="ebdfb-110">0</span><span class="sxs-lookup"><span data-stu-id="ebdfb-110">0</span></span>|<span data-ttu-id="ebdfb-111">关闭发出所有警告消息。</span><span class="sxs-lookup"><span data-stu-id="ebdfb-111">Turns off emission of all warning messages.</span></span>|  
|<span data-ttu-id="ebdfb-112">1</span><span class="sxs-lookup"><span data-stu-id="ebdfb-112">1</span></span>|<span data-ttu-id="ebdfb-113">显示严重警告消息。</span><span class="sxs-lookup"><span data-stu-id="ebdfb-113">Displays severe warning messages.</span></span>|  
|<span data-ttu-id="ebdfb-114">2</span><span class="sxs-lookup"><span data-stu-id="ebdfb-114">2</span></span>|<span data-ttu-id="ebdfb-115">显示等级 1 警告以及某些不太严重的警告，如有关隐藏类成员的警告。</span><span class="sxs-lookup"><span data-stu-id="ebdfb-115">Displays level 1 warnings plus certain, less-severe warnings, such as warnings about hiding class members.</span></span>|  
|<span data-ttu-id="ebdfb-116">3</span><span class="sxs-lookup"><span data-stu-id="ebdfb-116">3</span></span>|<span data-ttu-id="ebdfb-117">显示等级 2 警告以及某些不太严重的警告，如有关经常计算为 `true` 或 `false` 的表达式的警告。</span><span class="sxs-lookup"><span data-stu-id="ebdfb-117">Displays level 2 warnings plus certain, less-severe warnings, such as warnings about expressions that always evaluate to `true` or `false`.</span></span>|  
|<span data-ttu-id="ebdfb-118">4（默认值）</span><span class="sxs-lookup"><span data-stu-id="ebdfb-118">4 (the default)</span></span>|<span data-ttu-id="ebdfb-119">显示所有等级 3 警告以及信息性警告。</span><span class="sxs-lookup"><span data-stu-id="ebdfb-119">Displays all level 3 warnings plus informational warnings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ebdfb-120">备注</span><span class="sxs-lookup"><span data-stu-id="ebdfb-120">Remarks</span></span>  
 <span data-ttu-id="ebdfb-121">若要获取有关错误或警告的信息，可以在帮助索引中查找错误代码。</span><span class="sxs-lookup"><span data-stu-id="ebdfb-121">To get information about an error or warning, you can look up the error code in the Help Index.</span></span> <span data-ttu-id="ebdfb-122">有关获取错误或警告信息的其他方法，请参阅 [C# 编译器错误](../../../csharp/language-reference/compiler-messages/index.md)。</span><span class="sxs-lookup"><span data-stu-id="ebdfb-122">For other ways to get information about an error or warning, see [C# Compiler Errors](../../../csharp/language-reference/compiler-messages/index.md).</span></span>  
  
 <span data-ttu-id="ebdfb-123">使用 [-warnaserror](../../../csharp/language-reference/compiler-options/warnaserror-compiler-option.md) 将所有警告视为错误。</span><span class="sxs-lookup"><span data-stu-id="ebdfb-123">Use [-warnaserror](../../../csharp/language-reference/compiler-options/warnaserror-compiler-option.md) to treat all warnings as errors.</span></span> <span data-ttu-id="ebdfb-124">使用 [-nowarn](../../../csharp/language-reference/compiler-options/nowarn-compiler-option.md) 禁用某些警告。</span><span class="sxs-lookup"><span data-stu-id="ebdfb-124">Use [-nowarn](../../../csharp/language-reference/compiler-options/nowarn-compiler-option.md) to disable certain warnings.</span></span>  
  
 <span data-ttu-id="ebdfb-125">-w 是 -warn 的缩写形式。</span><span class="sxs-lookup"><span data-stu-id="ebdfb-125">**-w** is the short form of **-warn**.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="ebdfb-126">在 Visual Studio 开发环境中设置此编译器选项</span><span class="sxs-lookup"><span data-stu-id="ebdfb-126">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="ebdfb-127">打开项目的“属性”页。</span><span class="sxs-lookup"><span data-stu-id="ebdfb-127">Open the project's **Properties** page.</span></span>  
  
2.  <span data-ttu-id="ebdfb-128">单击“生成”属性页。</span><span class="sxs-lookup"><span data-stu-id="ebdfb-128">Click the **Build** property page.</span></span>  
  
3.  <span data-ttu-id="ebdfb-129">修改警告等级属性。</span><span class="sxs-lookup"><span data-stu-id="ebdfb-129">Modify the **Warning Level** property.</span></span>  
  
 <span data-ttu-id="ebdfb-130">有关如何以编程方式设置此编译器选项的信息，请参阅 <xref:VSLangProj80.CSharpProjectConfigurationProperties3.WarningLevel%2A>。</span><span class="sxs-lookup"><span data-stu-id="ebdfb-130">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.WarningLevel%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ebdfb-131">示例</span><span class="sxs-lookup"><span data-stu-id="ebdfb-131">Example</span></span>  
 <span data-ttu-id="ebdfb-132">编译 `in.cs` 并使编译器仅显示等级 1 警告：</span><span class="sxs-lookup"><span data-stu-id="ebdfb-132">Compile `in.cs` and have the compiler only display level 1 warnings:</span></span>  
  
```console  
csc -warn:1 in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="ebdfb-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="ebdfb-133">See also</span></span>

- [<span data-ttu-id="ebdfb-134">C# 编译器选项</span><span class="sxs-lookup"><span data-stu-id="ebdfb-134">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)
- [<span data-ttu-id="ebdfb-135">管理项目和解决方案属性</span><span class="sxs-lookup"><span data-stu-id="ebdfb-135">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
