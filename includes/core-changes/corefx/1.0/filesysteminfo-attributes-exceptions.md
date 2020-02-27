---
ms.openlocfilehash: 4091bdcf7d9ed8872aed5faa6e6d3ed143903787
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "77449386"
---
### <a name="unauthorizedaccessexception-thrown-by-filesysteminfoattributes"></a><span data-ttu-id="bf6e0-101">FileSystemInfo.Attributes 引发的 UnauthorizedAccessException</span><span class="sxs-lookup"><span data-stu-id="bf6e0-101">UnauthorizedAccessException thrown by FileSystemInfo.Attributes</span></span>

<span data-ttu-id="bf6e0-102">在 .NET Core 中，当调用方尝试设置文件属性值但没有写权限时，将引发 <xref:System.UnauthorizedAccessException>。</span><span class="sxs-lookup"><span data-stu-id="bf6e0-102">In .NET Core, an <xref:System.UnauthorizedAccessException> is thrown when the caller attempts to set a file attribute value but doesn't have write permission.</span></span>

#### <a name="change-description"></a><span data-ttu-id="bf6e0-103">更改描述</span><span class="sxs-lookup"><span data-stu-id="bf6e0-103">Change description</span></span>

<span data-ttu-id="bf6e0-104">在 .NET Framework 中，当调用方尝试在 <xref:System.IO.FileSystemInfo.Attributes?displayProperty=nameWithType> 中设置文件属性值但没有写权限时，将引发 <xref:System.ArgumentException>。</span><span class="sxs-lookup"><span data-stu-id="bf6e0-104">In .NET Framework, an <xref:System.ArgumentException> is thrown when the caller attempts to set a file attribute value in <xref:System.IO.FileSystemInfo.Attributes?displayProperty=nameWithType> but doesn't have write permission.</span></span> <span data-ttu-id="bf6e0-105">在 .NET Core 中，将改为引发 <xref:System.UnauthorizedAccessException>。</span><span class="sxs-lookup"><span data-stu-id="bf6e0-105">In .NET Core, an <xref:System.UnauthorizedAccessException> is thrown instead.</span></span> <span data-ttu-id="bf6e0-106">（在 .NET Core 中，如果调用方尝试设置无效的文件属性，则仍会引发 <xref:System.ArgumentException>。）</span><span class="sxs-lookup"><span data-stu-id="bf6e0-106">(In .NET Core, an <xref:System.ArgumentException> is still thrown if the caller attempts to set an invalid file attribute.)</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="bf6e0-107">引入的版本</span><span class="sxs-lookup"><span data-stu-id="bf6e0-107">Version introduced</span></span>

<span data-ttu-id="bf6e0-108">1.0</span><span class="sxs-lookup"><span data-stu-id="bf6e0-108">1.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="bf6e0-109">建议操作</span><span class="sxs-lookup"><span data-stu-id="bf6e0-109">Recommended action</span></span>

<span data-ttu-id="bf6e0-110">根据需要修改任何 `catch` 语句不是捕获 <xref:System.ArgumentException>，而是捕获或者除它之外还捕获 <xref:System.UnauthorizedAccessException>。</span><span class="sxs-lookup"><span data-stu-id="bf6e0-110">Modify any `catch` statements to catch an <xref:System.UnauthorizedAccessException> instead of, or in addition to, an <xref:System.ArgumentException>, as necessary.</span></span>

#### <a name="category"></a><span data-ttu-id="bf6e0-111">类别</span><span class="sxs-lookup"><span data-stu-id="bf6e0-111">Category</span></span>

<span data-ttu-id="bf6e0-112">CoreFx</span><span class="sxs-lookup"><span data-stu-id="bf6e0-112">CoreFx</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="bf6e0-113">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="bf6e0-113">Affected APIs</span></span>

- <xref:System.IO.FileSystemInfo.Attributes?displayProperty=nameWithType>

<!--

#### Affected APIs

- `P:System.IO.FileSystemInfo.Attributes`

-->
