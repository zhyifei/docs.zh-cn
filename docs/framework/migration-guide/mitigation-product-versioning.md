---
title: 缓解：产品版本控制
ms.date: 03/30/2017
ms.assetid: 1c4de9d7-9aba-427a-8f38-0ab9bfb8f85e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e75b838a2c6126fe82e97faac624a9ad6b7ea132
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64626233"
---
# <a name="mitigation-product-versioning"></a><span data-ttu-id="ad0b4-102">缓解：产品版本控制</span><span class="sxs-lookup"><span data-stu-id="ad0b4-102">Mitigation: Product Versioning</span></span>
<span data-ttu-id="ad0b4-103">在 [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] 和更高版本中，产品版本控制已更改，不再是早期版本的 .NET Framework（.NET Framework 4、4.5、4.5.1 和 4.5.2）。</span><span class="sxs-lookup"><span data-stu-id="ad0b4-103">In the [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] and later, product versioning has changed from the previous releases of the .NET Framework (the .NET Framework 4, 4.5, 4.5.1, and 4.5.2).</span></span>  
  
## <a name="product-versioning-changes"></a><span data-ttu-id="ad0b4-104">产品版本控制更改</span><span class="sxs-lookup"><span data-stu-id="ad0b4-104">Product versioning changes</span></span>  
 <span data-ttu-id="ad0b4-105">以下是详细更改：</span><span class="sxs-lookup"><span data-stu-id="ad0b4-105">The following are the detailed changes:</span></span>  
  
- <span data-ttu-id="ad0b4-106">`HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full` 键的 `Version` 项的值在 .NET Framework 4.6 及其点版本中已更改为 `4.6.`*xxxxx*，在 .NET Framework 4.7 中已更改为 `4.7.`*xxxxx*。</span><span class="sxs-lookup"><span data-stu-id="ad0b4-106">The value of the `Version` entry in the `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full` key has changed to `4.6.`*xxxxx* for the .NET Framework 4.6 and its point releases, and to `4.7.`*xxxxx* for the .NET Framework 4.7.</span></span> <span data-ttu-id="ad0b4-107">在 .NET Framework 4.5、4.5.1 和 4.5.2 中，它的格式为 `4.5.`*xxxxx*。</span><span class="sxs-lookup"><span data-stu-id="ad0b4-107">In the .NET Framework 4.5, 4.5.1, and 4.5.2, it had the format `4.5.`*xxxxx*.</span></span>  
  
- <span data-ttu-id="ad0b4-108">.NET Framework 文件的文件和产品版本控制在 .NET Framework 4.6 及其点版本中已从 `4.0.30319.x` 的早期版本控制方案更改为 `4.6.X.0`，在 .NET Framework 4.7 及其点版本中已更改为 `4.7.X.0`。</span><span class="sxs-lookup"><span data-stu-id="ad0b4-108">The file and product versioning for .NET Framework files has changed from the earlier versioning scheme of `4.0.30319.x` to `4.6.X.0` for the .NET Framework 4.6 and its point releases, and to `4.7.X.0` for the .NET Framework 4.7 and its point releases.</span></span> <span data-ttu-id="ad0b4-109">右键单击某个文件后，查看文件的“属性”时可以看到这些新值。</span><span class="sxs-lookup"><span data-stu-id="ad0b4-109">You can see these new values when you view the file's **Properties** after right-clicking on a file.</span></span>  
  
- <span data-ttu-id="ad0b4-110">对于 .NET Framework 4.6 及其点版本，托管程序集的 <xref:System.Reflection.AssemblyFileVersionAttribute> 和 <xref:System.Reflection.AssemblyInformationalVersionAttribute> 特性具有格式为 `4.6.X.0` 的 <xref:System.Version> 值，对于 .NET Framework 4.7，则为格式 `4.7.X.0`。</span><span class="sxs-lookup"><span data-stu-id="ad0b4-110">The <xref:System.Reflection.AssemblyFileVersionAttribute> and <xref:System.Reflection.AssemblyInformationalVersionAttribute> attributes for managed assemblies have <xref:System.Version> values in the form `4.6.X.0` for the .NET Framework 4.6 and its point releases, and `4.7.X.0` for the .NET Framework 4.7.</span></span>  
  
- <span data-ttu-id="ad0b4-111">在 [!INCLUDE[net_v46](../../../includes/net-v46-md.md)]、4.6.1、4.6.2 和 4.7 中，<xref:System.Environment.Version%2A?displayProperty=nameWithType> 属性将返回修正后的版本字符串 `4.0.30319.42000`。</span><span class="sxs-lookup"><span data-stu-id="ad0b4-111">In the [!INCLUDE[net_v46](../../../includes/net-v46-md.md)], 4.6.1, 4.6.2, and 4.7, the <xref:System.Environment.Version%2A?displayProperty=nameWithType> property returns the fixed version string `4.0.30319.42000`.</span></span> <span data-ttu-id="ad0b4-112">在 .NET Framework 4、4.5、4.5.1 和 4.5.2 中，它返回格式为 `4.0.30319.xxxxx` 的版本字符串（例如“4.0.30319.18010”）。</span><span class="sxs-lookup"><span data-stu-id="ad0b4-112">In the .NET Framework 4, 4.5, 4.5.1, and 4.5.2, it returns version strings in the format `4.0.30319.xxxxx` (for example, "4.0.30319.18010").</span></span> <span data-ttu-id="ad0b4-113">请注意，我们不建议应用程序代码对 <xref:System.Environment.Version%2A?displayProperty=nameWithType> 属性产生任何新的依赖关系。</span><span class="sxs-lookup"><span data-stu-id="ad0b4-113">Note that we do not recommend application code taking any new dependency on the <xref:System.Environment.Version%2A?displayProperty=nameWithType> property.</span></span>  
  
### <a name="handling-the-product-versioning-changes"></a><span data-ttu-id="ad0b4-114">处理产品版本控制更改</span><span class="sxs-lookup"><span data-stu-id="ad0b4-114">Handling the product versioning changes</span></span>  
 <span data-ttu-id="ad0b4-115">一般情况下，应用程序应依赖于用于检测诸如 .NET Framework 的运行时版本和安装目录等内容的推荐技术：</span><span class="sxs-lookup"><span data-stu-id="ad0b4-115">In general, applications should depend on the recommended techniques for detecting such things as the runtime version of the .NET Framework and the installation directory:</span></span>  
  
- <span data-ttu-id="ad0b4-116">要检测 .NET Framework 的运行时版本，请参阅[如何：确定已安装的 .NET Framework 版本](../../../docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md)。</span><span class="sxs-lookup"><span data-stu-id="ad0b4-116">To detect the runtime version of the .NET Framework, see [How to: Determine Which .NET Framework Versions Are Installed](../../../docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md).</span></span>  
  
- <span data-ttu-id="ad0b4-117">若要确定 .NET Framework 的安装路径，请使用 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full` 密钥中的 `InstallPath` 条目的值。</span><span class="sxs-lookup"><span data-stu-id="ad0b4-117">To determine the installation path for the .NET Framework, use the value of the `InstallPath` entry in the `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full` key.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="ad0b4-118">子项名称是 `NET Framework Setup`，而不是 `.NET Framework Setup`。</span><span class="sxs-lookup"><span data-stu-id="ad0b4-118">The subkey name is `NET Framework Setup`, not `.NET Framework Setup`.</span></span>  
  
- <span data-ttu-id="ad0b4-119">若要确定.NET Framework 公共语言运行时的目录路径，请调用 <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetRuntimeDirectory%2A?displayProperty=nameWithType> 方法。</span><span class="sxs-lookup"><span data-stu-id="ad0b4-119">To determine the directory path to the .NET Framework common language runtime, call the <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetRuntimeDirectory%2A?displayProperty=nameWithType> method.</span></span>  
  
- <span data-ttu-id="ad0b4-120">若要获取 CLR 版本，请调用 <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetSystemVersion%2A?displayProperty=nameWithType> 方法。</span><span class="sxs-lookup"><span data-stu-id="ad0b4-120">To get the CLR version, call the <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetSystemVersion%2A?displayProperty=nameWithType> method.</span></span>   <span data-ttu-id="ad0b4-121">对于 .NET Framework 4 及其点版本（.NET Framework 4.5、4.5.1、4.5.2 以及 [!INCLUDE[net_v46](../../../includes/net-v46-md.md)]、4.6.1、4.6.2 和 4.7），它将返回字符串 `v4.0.30319`。</span><span class="sxs-lookup"><span data-stu-id="ad0b4-121">For the .NET Framework 4 and its point releases (the .NET Framework 4.5, 4.5.1, 4.5.2, and [!INCLUDE[net_v46](../../../includes/net-v46-md.md)], 4.6.1, 4.6.2, and 4.7), it returns the string `v4.0.30319`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad0b4-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="ad0b4-122">See also</span></span>

- [<span data-ttu-id="ad0b4-123">运行时更改</span><span class="sxs-lookup"><span data-stu-id="ad0b4-123">Runtime Changes</span></span>](../../../docs/framework/migration-guide/runtime-changes-in-the-net-framework-4-6.md)
