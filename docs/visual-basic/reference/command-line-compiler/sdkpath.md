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
ms.openlocfilehash: 25368d23c398fb3674d5c2d75d4997f917a1c3d6
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69937356"
---
# <a name="-sdkpath"></a><span data-ttu-id="f2450-102">-sdkpath</span><span class="sxs-lookup"><span data-stu-id="f2450-102">-sdkpath</span></span>
<span data-ttu-id="f2450-103">指定 mscorlib.dll 和 Microsoft. .dll 的位置。</span><span class="sxs-lookup"><span data-stu-id="f2450-103">Specifies the location of mscorlib.dll and Microsoft.VisualBasic.dll.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2450-104">语法</span><span class="sxs-lookup"><span data-stu-id="f2450-104">Syntax</span></span>  
  
```  
-sdkpath:path  
```  
  
## <a name="arguments"></a><span data-ttu-id="f2450-105">自变量</span><span class="sxs-lookup"><span data-stu-id="f2450-105">Arguments</span></span>  
 `path`  
 <span data-ttu-id="f2450-106">包含要用于编译的 mscorlib.dll 和 Microsoft 的版本的目录。</span><span class="sxs-lookup"><span data-stu-id="f2450-106">The directory containing the versions of mscorlib.dll and Microsoft.VisualBasic.dll to use for compilation.</span></span> <span data-ttu-id="f2450-107">在加载之前, 不会对其进行验证。</span><span class="sxs-lookup"><span data-stu-id="f2450-107">This path is not verified until it is loaded.</span></span> <span data-ttu-id="f2450-108">如果目录名称包含空格, 则将其用引号 ("") 引起来。</span><span class="sxs-lookup"><span data-stu-id="f2450-108">Enclose the directory name in quotation marks (" ") if it contains a space.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f2450-109">备注</span><span class="sxs-lookup"><span data-stu-id="f2450-109">Remarks</span></span>  
 <span data-ttu-id="f2450-110">此选项告知 Visual Basic 编译器从非默认位置加载 mscorlib.dll 和 Microsoft. .dll 文件。</span><span class="sxs-lookup"><span data-stu-id="f2450-110">This option tells the Visual Basic compiler to load the mscorlib.dll and Microsoft.VisualBasic.dll files from a non-default location.</span></span> <span data-ttu-id="f2450-111">选项设计为与[-netcf](../../../visual-basic/reference/command-line-compiler/netcf.md)一起使用。 `-sdkpath`</span><span class="sxs-lookup"><span data-stu-id="f2450-111">The `-sdkpath` option was designed to be used with [-netcf](../../../visual-basic/reference/command-line-compiler/netcf.md).</span></span> <span data-ttu-id="f2450-112">.NET Compact Framework 使用这些支持库的不同版本, 以避免使用在设备上找不到的类型和语言功能。</span><span class="sxs-lookup"><span data-stu-id="f2450-112">The .NET Compact Framework uses different versions of these support libraries to avoid the use of types and language features not found on the devices.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f2450-113">此`-sdkpath`选项在 Visual Studio 开发环境中不可用; 它仅在从命令行编译时可用。</span><span class="sxs-lookup"><span data-stu-id="f2450-113">The `-sdkpath` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span> <span data-ttu-id="f2450-114">加载`-sdkpath` Visual Basic 设备项目时, 设置选项。</span><span class="sxs-lookup"><span data-stu-id="f2450-114">The `-sdkpath` option is set when a Visual Basic device project is loaded.</span></span>  
  
 <span data-ttu-id="f2450-115">您可以通过使用`-vbruntime`编译器选项指定编译器应编译, 而无需引用 Visual Basic 运行时库。</span><span class="sxs-lookup"><span data-stu-id="f2450-115">You can specify that the compiler should compile without a reference to the Visual Basic Runtime Library by using the `-vbruntime` compiler option.</span></span> <span data-ttu-id="f2450-116">有关详细信息, 请参阅[-vbruntime](../../../visual-basic/reference/command-line-compiler/vbruntime.md)。</span><span class="sxs-lookup"><span data-stu-id="f2450-116">For more information, see [-vbruntime](../../../visual-basic/reference/command-line-compiler/vbruntime.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f2450-117">示例</span><span class="sxs-lookup"><span data-stu-id="f2450-117">Example</span></span>  
 <span data-ttu-id="f2450-118">下面的代码使用`Myfile.vb` .NET Compact Framework 进行编译, 其中使用了 C 驱动器上 .NET Compact Framework 的默认安装目录中的 mscorlib.dll 和 Microsoft. .dll 版本。</span><span class="sxs-lookup"><span data-stu-id="f2450-118">The following code compiles `Myfile.vb` with the .NET Compact Framework, using the versions of Mscorlib.dll and Microsoft.VisualBasic.dll found in the default installation directory of the .NET Compact Framework on the C drive.</span></span> <span data-ttu-id="f2450-119">通常, 您将使用最新版本的 .NET Compact Framework。</span><span class="sxs-lookup"><span data-stu-id="f2450-119">Typically, you would use the most recent version of the .NET Compact Framework.</span></span>  
  
```console
vbc -netcf -sdkpath:"c:\Program Files\Microsoft Visual Studio .NET 2003\CompactFrameworkSDK\v1.0.5000\Windows CE " myfile.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="f2450-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="f2450-120">See also</span></span>

- [<span data-ttu-id="f2450-121">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="f2450-121">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="f2450-122">示例编译命令行</span><span class="sxs-lookup"><span data-stu-id="f2450-122">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="f2450-123">-netcf</span><span class="sxs-lookup"><span data-stu-id="f2450-123">-netcf</span></span>](../../../visual-basic/reference/command-line-compiler/netcf.md)
- [<span data-ttu-id="f2450-124">-vbruntime</span><span class="sxs-lookup"><span data-stu-id="f2450-124">-vbruntime</span></span>](../../../visual-basic/reference/command-line-compiler/vbruntime.md)
