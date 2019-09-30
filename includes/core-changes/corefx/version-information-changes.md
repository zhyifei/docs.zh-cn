---
ms.openlocfilehash: 2a751acc129ebd1c917b87f8083ffef72c7d8c17
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/24/2019
ms.locfileid: "71216353"
---
### <a name="apis-that-report-version-now-report-product-and-not-file-version"></a><span data-ttu-id="81dc3-101">报告版本的 API 现报告的是产品版本而不是文件版本</span><span class="sxs-lookup"><span data-stu-id="81dc3-101">APIs that report version now report product and not file version</span></span>

<span data-ttu-id="81dc3-102">返回 .NET Core 中的版本的很多 API 现在返回的是产品版本，而不是文件版本。</span><span class="sxs-lookup"><span data-stu-id="81dc3-102">Many of the APIs that return versions in .NET Core now returned the product version rather than the file version.</span></span>

#### <a name="change-description"></a><span data-ttu-id="81dc3-103">更改描述</span><span class="sxs-lookup"><span data-stu-id="81dc3-103">Change description</span></span>

<span data-ttu-id="81dc3-104">在 .NET Core 2.2 及更低版本中，<xref:System.Environment.Version?displayProperty=nameWithType> 和 <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType> 等方法以及 .NET Core 程序集的“文件属性”对话框反映的都是文件版本。</span><span class="sxs-lookup"><span data-stu-id="81dc3-104">In .NET Core 2.2 and previous versions, methods such as <xref:System.Environment.Version?displayProperty=nameWithType>, <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType>, and the file properties dialog for .NET Core assemblies reflect the file version.</span></span> <span data-ttu-id="81dc3-105">自 .NET Core 3.0 起，它们反映的是产品版本。</span><span class="sxs-lookup"><span data-stu-id="81dc3-105">Starting with .NET Core 3.0, they reflect the product version.</span></span>

<span data-ttu-id="81dc3-106">下图展示了由“Windows 资源管理器”文件属性对话框显示的 .NET Core 2.2（左侧）与 .NET Core 3.0（右侧）的 System.Runtime.dll 程序集版本信息区别   。</span><span class="sxs-lookup"><span data-stu-id="81dc3-106">The following figure illustrates the difference in version information for the *System.Runtime.dll* assembly for .NET Core 2.2 (on the left) and .NET Core 3.0 (on the right) as displayed by the **Windows Explorer** file properties dialog.</span></span>

![产品版本信息中的差异](~/docs/images/core-changes/corefx/version-information-changes/file-details.png)

#### <a name="version-introduced"></a><span data-ttu-id="81dc3-108">引入的版本</span><span class="sxs-lookup"><span data-stu-id="81dc3-108">Version introduced</span></span>

<span data-ttu-id="81dc3-109">3.0</span><span class="sxs-lookup"><span data-stu-id="81dc3-109">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="81dc3-110">建议的操作</span><span class="sxs-lookup"><span data-stu-id="81dc3-110">Recommended action</span></span>

<span data-ttu-id="81dc3-111">无。</span><span class="sxs-lookup"><span data-stu-id="81dc3-111">None.</span></span> <span data-ttu-id="81dc3-112">此更改会使版本检测变得直观而非退化。</span><span class="sxs-lookup"><span data-stu-id="81dc3-112">This change should make version detection intuitive rather than obtuse.</span></span>

#### <a name="category"></a><span data-ttu-id="81dc3-113">类别</span><span class="sxs-lookup"><span data-stu-id="81dc3-113">Category</span></span>

<span data-ttu-id="81dc3-114">CoreFx</span><span class="sxs-lookup"><span data-stu-id="81dc3-114">CoreFx</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="81dc3-115">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="81dc3-115">Affected APIs</span></span>

- <xref:System.Environment.Version?displayProperty=nameWithType>
- <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType>

<!--

### Affected APIs

- `P:System.Environment.Version`
- `P:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription`

-->
