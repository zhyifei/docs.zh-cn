---
title: -nostdlib（C# 编译器选项）
ms.date: 12/20/2019
f1_keywords:
- /nostdlib
helpviewer_keywords:
- nostdlib compiler option [C#]
- -nostdlib compiler option [C#]
- /nostdlib compiler option [C#]
ms.assetid: ec197989-fa49-4725-a455-e06b551eb65f
ms.openlocfilehash: ad8a2b5fc87dd7beee86d96331cf3961315be533
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/25/2019
ms.locfileid: "75345079"
---
# <a name="-nostdlib-c-compiler-options"></a><span data-ttu-id="0ffb2-102">-nostdlib（C# 编译器选项）</span><span class="sxs-lookup"><span data-stu-id="0ffb2-102">-nostdlib (C# Compiler Options)</span></span>

<span data-ttu-id="0ffb2-103">-nostdlib 可防止导入 mscorlib.dll，后者定义了整个 System 命名空间  。</span><span class="sxs-lookup"><span data-stu-id="0ffb2-103">**-nostdlib** prevents the import of mscorlib.dll, which defines the entire System namespace.</span></span>

## <a name="syntax"></a><span data-ttu-id="0ffb2-104">语法</span><span class="sxs-lookup"><span data-stu-id="0ffb2-104">Syntax</span></span>

```console
-nostdlib[+ | -]
```

## <a name="remarks"></a><span data-ttu-id="0ffb2-105">备注</span><span class="sxs-lookup"><span data-stu-id="0ffb2-105">Remarks</span></span>

<span data-ttu-id="0ffb2-106">如果你想要定义或创建自己的 System 命名空间和对象，请使用此选项。</span><span class="sxs-lookup"><span data-stu-id="0ffb2-106">Use this option if you want to define or create your own System namespace and objects.</span></span>

<span data-ttu-id="0ffb2-107">如果未指定 -nostdlib，则 mscorlib.dll 将被导入到程序中（与指定 -nostdlib- 相同）   。</span><span class="sxs-lookup"><span data-stu-id="0ffb2-107">If you do not specify **-nostdlib**, mscorlib.dll is imported into your program (same as specifying **-nostdlib-**).</span></span> <span data-ttu-id="0ffb2-108">指定 -nostdlib 与指定 -nostdlib+ 相同   。</span><span class="sxs-lookup"><span data-stu-id="0ffb2-108">Specifying **-nostdlib** is the same as specifying **-nostdlib+**.</span></span>

### <a name="to-set-this-compiler-option-in-visual-studio"></a><span data-ttu-id="0ffb2-109">在 Visual Studio 中设置此编译器选项</span><span class="sxs-lookup"><span data-stu-id="0ffb2-109">To set this compiler option in Visual Studio</span></span>

> [!NOTE]
> <span data-ttu-id="0ffb2-110">以下说明仅适用于 Visual Studio 2015（及更早版本）。</span><span class="sxs-lookup"><span data-stu-id="0ffb2-110">The following instructions apply to Visual Studio 2015 (and earlier versions) only.</span></span> <span data-ttu-id="0ffb2-111">Visual Studio 的新版本中不存在“不引用 mscorlib.dll”  生成属性。</span><span class="sxs-lookup"><span data-stu-id="0ffb2-111">The **Do not reference mscorlib.dll** build property doesn't exist in newer versions of Visual Studio.</span></span>

1. <span data-ttu-id="0ffb2-112">打开项目的“属性”  页。</span><span class="sxs-lookup"><span data-stu-id="0ffb2-112">Open the **Properties** page for the project.</span></span>

2. <span data-ttu-id="0ffb2-113">单击“生成”  属性页。</span><span class="sxs-lookup"><span data-stu-id="0ffb2-113">Click the **Build** properties page.</span></span>

3. <span data-ttu-id="0ffb2-114">单击“高级”  按钮。</span><span class="sxs-lookup"><span data-stu-id="0ffb2-114">Click the **Advanced** button.</span></span>

4. <span data-ttu-id="0ffb2-115">修改“不引用 mscorlib.dll”  属性。</span><span class="sxs-lookup"><span data-stu-id="0ffb2-115">Modify the **Do not reference mscorlib.dll** property.</span></span>

### <a name="to-set-this-compiler-option-programmatically"></a><span data-ttu-id="0ffb2-116">以编程方式设置此编译器选项</span><span class="sxs-lookup"><span data-stu-id="0ffb2-116">To set this compiler option programmatically</span></span>

<span data-ttu-id="0ffb2-117">有关如何以编程方式设置此编译器选项的信息，请参阅 <xref:VSLangProj80.CSharpProjectConfigurationProperties3.NoStdLib%2A>。</span><span class="sxs-lookup"><span data-stu-id="0ffb2-117">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.NoStdLib%2A>.</span></span>

## <a name="see-also"></a><span data-ttu-id="0ffb2-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="0ffb2-118">See also</span></span>

- [<span data-ttu-id="0ffb2-119">C# 编译器选项</span><span class="sxs-lookup"><span data-stu-id="0ffb2-119">C# Compiler Options</span></span>](./index.md)
