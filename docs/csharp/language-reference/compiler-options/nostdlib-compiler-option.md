---
title: -nostdlib（C# 编译器选项）
ms.date: 07/20/2015
f1_keywords:
- /nostdlib
helpviewer_keywords:
- nostdlib compiler option [C#]
- -nostdlib compiler option [C#]
- /nostdlib compiler option [C#]
ms.assetid: ec197989-fa49-4725-a455-e06b551eb65f
ms.openlocfilehash: 70007c74efe9a41bdfc15e8fa7daf3c8fc0221ed
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2018
ms.locfileid: "42935519"
---
# <a name="-nostdlib-c-compiler-options"></a><span data-ttu-id="7e0aa-102">-nostdlib（C# 编译器选项）</span><span class="sxs-lookup"><span data-stu-id="7e0aa-102">-nostdlib (C# Compiler Options)</span></span>

<span data-ttu-id="7e0aa-103">-nostdlib 可防止导入 mscorlib.dll，后者定义了整个 System 命名空间。</span><span class="sxs-lookup"><span data-stu-id="7e0aa-103">**-nostdlib** prevents the import of mscorlib.dll, which defines the entire System namespace.</span></span>

## <a name="syntax"></a><span data-ttu-id="7e0aa-104">语法</span><span class="sxs-lookup"><span data-stu-id="7e0aa-104">Syntax</span></span>

```console
-nostdlib[+ | -]
```

## <a name="remarks"></a><span data-ttu-id="7e0aa-105">备注</span><span class="sxs-lookup"><span data-stu-id="7e0aa-105">Remarks</span></span>

<span data-ttu-id="7e0aa-106">如果你想要定义或创建自己的 System 命名空间和对象，请使用此选项。</span><span class="sxs-lookup"><span data-stu-id="7e0aa-106">Use this option if you want to define or create your own System namespace and objects.</span></span>

<span data-ttu-id="7e0aa-107">如果未指定 -nostdlib，则 mscorlib.dll 将被导入到程序中（与指定 -nostdlib- 相同）。</span><span class="sxs-lookup"><span data-stu-id="7e0aa-107">If you do not specify **-nostdlib**, mscorlib.dll is imported into your program (same as specifying **-nostdlib-**).</span></span> <span data-ttu-id="7e0aa-108">指定 -nostdlib 与指定 -nostdlib+ 相同。</span><span class="sxs-lookup"><span data-stu-id="7e0aa-108">Specifying **-nostdlib** is the same as specifying **-nostdlib+**.</span></span>

### <a name="to-set-this-compiler-option-in-visual-studio"></a><span data-ttu-id="7e0aa-109">在 Visual Studio 中设置此编译器选项</span><span class="sxs-lookup"><span data-stu-id="7e0aa-109">To set this compiler option in Visual Studio</span></span>

> [!NOTE]
> <span data-ttu-id="7e0aa-110">以下说明仅适用于 Visual Studio 2015（及更早版本）。</span><span class="sxs-lookup"><span data-stu-id="7e0aa-110">The following instructions apply to Visual Studio 2015 (and earlier versions) only.</span></span> <span data-ttu-id="7e0aa-111">Visual Studio 2017 中不存在“不引用 mscorlib.dll”生成属性。</span><span class="sxs-lookup"><span data-stu-id="7e0aa-111">The **Do not reference mscorlib.dll** build property doesn't exist in Visual Studio 2017.</span></span>

1. <span data-ttu-id="7e0aa-112">打开项目的“属性”  页。</span><span class="sxs-lookup"><span data-stu-id="7e0aa-112">Open the **Properties** page for the project.</span></span>

2. <span data-ttu-id="7e0aa-113">单击“生成”  属性页。</span><span class="sxs-lookup"><span data-stu-id="7e0aa-113">Click the **Build** properties page.</span></span>

3. <span data-ttu-id="7e0aa-114">单击 **“高级”** 按钮。</span><span class="sxs-lookup"><span data-stu-id="7e0aa-114">Click the **Advanced** button.</span></span>

4. <span data-ttu-id="7e0aa-115">修改“不引用 mscorlib.dll”  属性。</span><span class="sxs-lookup"><span data-stu-id="7e0aa-115">Modify the **Do not reference mscorlib.dll** property.</span></span>

### <a name="to-set-this-compiler-option-programmatically"></a><span data-ttu-id="7e0aa-116">以编程方式设置此编译器选项</span><span class="sxs-lookup"><span data-stu-id="7e0aa-116">To set this compiler option programmatically</span></span>

<span data-ttu-id="7e0aa-117">有关如何以编程方式设置此编译器选项的信息，请参阅 <xref:VSLangProj80.CSharpProjectConfigurationProperties3.NoStdLib%2A>。</span><span class="sxs-lookup"><span data-stu-id="7e0aa-117">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.NoStdLib%2A>.</span></span>

## <a name="see-also"></a><span data-ttu-id="7e0aa-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="7e0aa-118">See Also</span></span>

- [<span data-ttu-id="7e0aa-119">C# 编译器选项</span><span class="sxs-lookup"><span data-stu-id="7e0aa-119">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)
