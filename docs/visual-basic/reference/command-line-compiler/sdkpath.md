---
title: -sdkpath
ms.date: 07/20/2015
f1_keywords:
- sdkpath
- -sdkpath
helpviewer_keywords:
- -sdkpath compiler option [Visual Basic]
- /sdkpath compiler option [Visual Basic]
- sdkpath compiler option [Visual Basic]
ms.assetid: fec8a3f1-b791-4a37-8af7-344859f8212d
ms.openlocfilehash: 46cec7ac3cb78c4fc97e299535f9085eff6daeff
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004689"
---
# <a name="-sdkpath"></a><span data-ttu-id="135b3-102">-sdkpath</span><span class="sxs-lookup"><span data-stu-id="135b3-102">-sdkpath</span></span>
<span data-ttu-id="135b3-103">指定 mscorlib.dll 和 Microsoft. .dll 的位置。</span><span class="sxs-lookup"><span data-stu-id="135b3-103">Specifies the location of mscorlib.dll and Microsoft.VisualBasic.dll.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="135b3-104">语法</span><span class="sxs-lookup"><span data-stu-id="135b3-104">Syntax</span></span>  
  
```console  
-sdkpath:path  
```  
  
## <a name="arguments"></a><span data-ttu-id="135b3-105">参数</span><span class="sxs-lookup"><span data-stu-id="135b3-105">Arguments</span></span>  
 `path`  
 <span data-ttu-id="135b3-106">包含要用于编译的 mscorlib.dll 和 Microsoft 的版本的目录。</span><span class="sxs-lookup"><span data-stu-id="135b3-106">The directory containing the versions of mscorlib.dll and Microsoft.VisualBasic.dll to use for compilation.</span></span> <span data-ttu-id="135b3-107">在加载之前，不会对其进行验证。</span><span class="sxs-lookup"><span data-stu-id="135b3-107">This path is not verified until it is loaded.</span></span> <span data-ttu-id="135b3-108">如果目录名称包含空格，则将其用引号（""）引起来。</span><span class="sxs-lookup"><span data-stu-id="135b3-108">Enclose the directory name in quotation marks (" ") if it contains a space.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="135b3-109">备注</span><span class="sxs-lookup"><span data-stu-id="135b3-109">Remarks</span></span>  
 <span data-ttu-id="135b3-110">此选项告知 Visual Basic 编译器从非默认位置加载 mscorlib.dll 和 Microsoft. .dll 文件。</span><span class="sxs-lookup"><span data-stu-id="135b3-110">This option tells the Visual Basic compiler to load the mscorlib.dll and Microsoft.VisualBasic.dll files from a non-default location.</span></span> <span data-ttu-id="135b3-111">@No__t-0 选项设计为与[-netcf](../../../visual-basic/reference/command-line-compiler/netcf.md)一起使用。</span><span class="sxs-lookup"><span data-stu-id="135b3-111">The `-sdkpath` option was designed to be used with [-netcf](../../../visual-basic/reference/command-line-compiler/netcf.md).</span></span> <span data-ttu-id="135b3-112">.NET Compact Framework 使用这些支持库的不同版本，以避免使用在设备上找不到的类型和语言功能。</span><span class="sxs-lookup"><span data-stu-id="135b3-112">The .NET Compact Framework uses different versions of these support libraries to avoid the use of types and language features not found on the devices.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="135b3-113">在 Visual Studio 开发环境中，不能使用 `-sdkpath` 选项;仅当从命令行进行编译时，它才可用。</span><span class="sxs-lookup"><span data-stu-id="135b3-113">The `-sdkpath` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span> <span data-ttu-id="135b3-114">加载 Visual Basic 设备项目时，设置 `-sdkpath` 选项。</span><span class="sxs-lookup"><span data-stu-id="135b3-114">The `-sdkpath` option is set when a Visual Basic device project is loaded.</span></span>  
  
 <span data-ttu-id="135b3-115">您可以通过使用 `-vbruntime` 编译器选项指定编译器应编译，而无需引用 Visual Basic 运行时库。</span><span class="sxs-lookup"><span data-stu-id="135b3-115">You can specify that the compiler should compile without a reference to the Visual Basic Runtime Library by using the `-vbruntime` compiler option.</span></span> <span data-ttu-id="135b3-116">有关详细信息，请参阅[-vbruntime](../../../visual-basic/reference/command-line-compiler/vbruntime.md)。</span><span class="sxs-lookup"><span data-stu-id="135b3-116">For more information, see [-vbruntime](../../../visual-basic/reference/command-line-compiler/vbruntime.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="135b3-117">示例</span><span class="sxs-lookup"><span data-stu-id="135b3-117">Example</span></span>  
 <span data-ttu-id="135b3-118">下面的代码使用 C 驱动器上 .NET Compact Framework 的默认安装目录中的 Mscorlib.dll 和 Microsoft .NET Compact Framework 的版本，将 `Myfile.vb` 编译为。</span><span class="sxs-lookup"><span data-stu-id="135b3-118">The following code compiles `Myfile.vb` with the .NET Compact Framework, using the versions of Mscorlib.dll and Microsoft.VisualBasic.dll found in the default installation directory of the .NET Compact Framework on the C drive.</span></span> <span data-ttu-id="135b3-119">通常，您将使用最新版本的 .NET Compact Framework。</span><span class="sxs-lookup"><span data-stu-id="135b3-119">Typically, you would use the most recent version of the .NET Compact Framework.</span></span>  
  
```console
vbc -netcf -sdkpath:"c:\Program Files\Microsoft Visual Studio .NET 2003\CompactFrameworkSDK\v1.0.5000\Windows CE " myfile.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="135b3-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="135b3-120">See also</span></span>

- [<span data-ttu-id="135b3-121">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="135b3-121">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="135b3-122">示例编译命令行</span><span class="sxs-lookup"><span data-stu-id="135b3-122">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="135b3-123">-netcf</span><span class="sxs-lookup"><span data-stu-id="135b3-123">-netcf</span></span>](../../../visual-basic/reference/command-line-compiler/netcf.md)
- [<span data-ttu-id="135b3-124">-vbruntime</span><span class="sxs-lookup"><span data-stu-id="135b3-124">-vbruntime</span></span>](../../../visual-basic/reference/command-line-compiler/vbruntime.md)
