---
ms.openlocfilehash: 2ea9abca7578c2ddf92712a1c597f8f1ff4a5c0c
ms.sourcegitcommit: 348bb052d5cef109a61a3d5253faa5d7167d55ac
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2020
ms.locfileid: "82021816"
---
### <a name="unauthorizedaccessexception-thrown-by-filesysteminfoattributes"></a><span data-ttu-id="327e3-101">FileSystemInfo.Attributes 引发的 UnauthorizedAccessException</span><span class="sxs-lookup"><span data-stu-id="327e3-101">UnauthorizedAccessException thrown by FileSystemInfo.Attributes</span></span>

<span data-ttu-id="327e3-102">在 .NET Core 中，当调用方尝试设置文件属性值但没有写权限时，将引发 <xref:System.UnauthorizedAccessException>。</span><span class="sxs-lookup"><span data-stu-id="327e3-102">In .NET Core, an <xref:System.UnauthorizedAccessException> is thrown when the caller attempts to set a file attribute value but doesn't have write permission.</span></span>

#### <a name="change-description"></a><span data-ttu-id="327e3-103">更改描述</span><span class="sxs-lookup"><span data-stu-id="327e3-103">Change description</span></span>

<span data-ttu-id="327e3-104">在 .NET Framework 中，当调用方尝试在 <xref:System.IO.FileSystemInfo.Attributes?displayProperty=nameWithType> 中设置文件属性值但没有写权限时，将引发 <xref:System.ArgumentException>。</span><span class="sxs-lookup"><span data-stu-id="327e3-104">In .NET Framework, an <xref:System.ArgumentException> is thrown when the caller attempts to set a file attribute value in <xref:System.IO.FileSystemInfo.Attributes?displayProperty=nameWithType> but doesn't have write permission.</span></span> <span data-ttu-id="327e3-105">在 .NET Core 中，将改为引发 <xref:System.UnauthorizedAccessException>。</span><span class="sxs-lookup"><span data-stu-id="327e3-105">In .NET Core, an <xref:System.UnauthorizedAccessException> is thrown instead.</span></span> <span data-ttu-id="327e3-106">（在 .NET Core 中，如果调用方尝试设置无效的文件属性，则仍会引发 <xref:System.ArgumentException>。）</span><span class="sxs-lookup"><span data-stu-id="327e3-106">(In .NET Core, an <xref:System.ArgumentException> is still thrown if the caller attempts to set an invalid file attribute.)</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="327e3-107">引入的版本</span><span class="sxs-lookup"><span data-stu-id="327e3-107">Version introduced</span></span>

<span data-ttu-id="327e3-108">1.0</span><span class="sxs-lookup"><span data-stu-id="327e3-108">1.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="327e3-109">建议操作</span><span class="sxs-lookup"><span data-stu-id="327e3-109">Recommended action</span></span>

<span data-ttu-id="327e3-110">根据需要修改任何 `catch` 语句不是捕获 <xref:System.ArgumentException>，而是捕获或者除它之外还捕获 <xref:System.UnauthorizedAccessException>。</span><span class="sxs-lookup"><span data-stu-id="327e3-110">Modify any `catch` statements to catch an <xref:System.UnauthorizedAccessException> instead of, or in addition to, an <xref:System.ArgumentException>, as necessary.</span></span>

#### <a name="category"></a><span data-ttu-id="327e3-111">类别</span><span class="sxs-lookup"><span data-stu-id="327e3-111">Category</span></span>

<span data-ttu-id="327e3-112">Core .NET 库</span><span class="sxs-lookup"><span data-stu-id="327e3-112">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="327e3-113">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="327e3-113">Affected APIs</span></span>

- <xref:System.IO.FileSystemInfo.Attributes?displayProperty=nameWithType>

<!--

#### Affected APIs

- `P:System.IO.FileSystemInfo.Attributes`

-->
