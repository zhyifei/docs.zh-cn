---
ms.openlocfilehash: 2dd97fcce13ed1ac7baf4cd02f5881d31d7a9c4b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235085"
---
### <a name="xslt-forward-compat-now-works"></a><span data-ttu-id="f745a-101">XSLT 向前兼容现在有效</span><span class="sxs-lookup"><span data-stu-id="f745a-101">XSLT forward compat now works</span></span>

|   |   |
|---|---|
|<span data-ttu-id="f745a-102">详细信息</span><span class="sxs-lookup"><span data-stu-id="f745a-102">Details</span></span>|<span data-ttu-id="f745a-103">在 .NET Framework 4 中，XSLT 1.0 向前兼容性具有以下问题：</span><span class="sxs-lookup"><span data-stu-id="f745a-103">In the .NET Framework 4, XSLT 1.0 forward compatibility had the following issues:</span></span><ul><li><span data-ttu-id="f745a-104">如果其版本设置为 2.0，并且分析器遇到无法识别的 XSLT 1.0 构造，则无法加载样式表。</span><span class="sxs-lookup"><span data-stu-id="f745a-104">Loading a style sheet failed if its version was set to 2.0 and the parser encountered an unrecognized XSLT 1.0 construct.</span></span></li><li><span data-ttu-id="f745a-105">如果将样式表版本设置为 1.1，则 <code>xsl:sort</code> 构造无法对数据进行排序。</span><span class="sxs-lookup"><span data-stu-id="f745a-105">The <code>xsl:sort</code> construct failed to sort data if the style sheet version was set to 1.1.</span></span></li></ul><span data-ttu-id="f745a-106">在 .NET Framework 4.5 中，这些问题已修复，并且 XSLT 1.0 向前兼容性模式可正常工作。</span><span class="sxs-lookup"><span data-stu-id="f745a-106">In the .NET Framework 4.5, these issues have been fixed, and XSLT 1.0 forward compatibility mode works properly.</span></span>|
|<span data-ttu-id="f745a-107">建议</span><span class="sxs-lookup"><span data-stu-id="f745a-107">Suggestion</span></span>|<span data-ttu-id="f745a-108">大多数应用应该不受影响，但由于遵循 xsl:sort，某些情况下数据排序将会不同。</span><span class="sxs-lookup"><span data-stu-id="f745a-108">Most apps should be unaffected, however data will be sorted differently in some cases now that xsl:sort is respected.</span></span> <span data-ttu-id="f745a-109">如果在 1.1 样式表中使用 <code>xsl:sort</code>，请确定应用不依赖于未排序数据。</span><span class="sxs-lookup"><span data-stu-id="f745a-109">If <code>xsl:sort</code> is used in 1.1 style sheets, confirm that apps were not depending on the unsorted order of data.</span></span> <span data-ttu-id="f745a-110">如果应用依赖于 4.0 排序行为，请从样式表删除 <code>xsl:sort</code>。</span><span class="sxs-lookup"><span data-stu-id="f745a-110">If apps rely on the 4.0 sorting behavior, remove <code>xsl:sort</code> from the style sheet.</span></span>|
|<span data-ttu-id="f745a-111">范围</span><span class="sxs-lookup"><span data-stu-id="f745a-111">Scope</span></span>|<span data-ttu-id="f745a-112">边缘</span><span class="sxs-lookup"><span data-stu-id="f745a-112">Edge</span></span>|
|<span data-ttu-id="f745a-113">版本</span><span class="sxs-lookup"><span data-stu-id="f745a-113">Version</span></span>|<span data-ttu-id="f745a-114">4.5</span><span class="sxs-lookup"><span data-stu-id="f745a-114">4.5</span></span>|
|<span data-ttu-id="f745a-115">类型</span><span class="sxs-lookup"><span data-stu-id="f745a-115">Type</span></span>|<span data-ttu-id="f745a-116">运行时</span><span class="sxs-lookup"><span data-stu-id="f745a-116">Runtime</span></span>|
|<span data-ttu-id="f745a-117">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="f745a-117">Affected APIs</span></span>|<ul><li><xref:System.Xml.Xsl.XslCompiledTransform?displayProperty=nameWithType></li></ul>|
