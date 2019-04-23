---
ms.openlocfilehash: 2dd97fcce13ed1ac7baf4cd02f5881d31d7a9c4b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59803297"
---
### <a name="xslt-forward-compat-now-works"></a><span data-ttu-id="5ce84-101">XSLT 向前兼容现在有效</span><span class="sxs-lookup"><span data-stu-id="5ce84-101">XSLT forward compat now works</span></span>

|   |   |
|---|---|
|<span data-ttu-id="5ce84-102">详细信息</span><span class="sxs-lookup"><span data-stu-id="5ce84-102">Details</span></span>|<span data-ttu-id="5ce84-103">在 .NET Framework 4 中，XSLT 1.0 向前兼容性具有以下问题：</span><span class="sxs-lookup"><span data-stu-id="5ce84-103">In the .NET Framework 4, XSLT 1.0 forward compatibility had the following issues:</span></span><ul><li><span data-ttu-id="5ce84-104">如果其版本设置为 2.0，并且分析器遇到无法识别的 XSLT 1.0 构造，则无法加载样式表。</span><span class="sxs-lookup"><span data-stu-id="5ce84-104">Loading a style sheet failed if its version was set to 2.0 and the parser encountered an unrecognized XSLT 1.0 construct.</span></span></li><li><span data-ttu-id="5ce84-105">如果将样式表版本设置为 1.1，则 <code>xsl:sort</code> 构造无法对数据进行排序。</span><span class="sxs-lookup"><span data-stu-id="5ce84-105">The <code>xsl:sort</code> construct failed to sort data if the style sheet version was set to 1.1.</span></span></li></ul><span data-ttu-id="5ce84-106">在 .NET Framework 4.5 中，这些问题已修复，并且 XSLT 1.0 向前兼容性模式可正常工作。</span><span class="sxs-lookup"><span data-stu-id="5ce84-106">In the .NET Framework 4.5, these issues have been fixed, and XSLT 1.0 forward compatibility mode works properly.</span></span>|
|<span data-ttu-id="5ce84-107">建议</span><span class="sxs-lookup"><span data-stu-id="5ce84-107">Suggestion</span></span>|<span data-ttu-id="5ce84-108">大多数应用应该不受影响，但由于遵循 xsl:sort，某些情况下数据排序将会不同。</span><span class="sxs-lookup"><span data-stu-id="5ce84-108">Most apps should be unaffected, however data will be sorted differently in some cases now that xsl:sort is respected.</span></span> <span data-ttu-id="5ce84-109">如果在 1.1 样式表中使用 <code>xsl:sort</code>，请确定应用不依赖于未排序数据。</span><span class="sxs-lookup"><span data-stu-id="5ce84-109">If <code>xsl:sort</code> is used in 1.1 style sheets, confirm that apps were not depending on the unsorted order of data.</span></span> <span data-ttu-id="5ce84-110">如果应用依赖于 4.0 排序行为，请从样式表删除 <code>xsl:sort</code>。</span><span class="sxs-lookup"><span data-stu-id="5ce84-110">If apps rely on the 4.0 sorting behavior, remove <code>xsl:sort</code> from the style sheet.</span></span>|
|<span data-ttu-id="5ce84-111">范围</span><span class="sxs-lookup"><span data-stu-id="5ce84-111">Scope</span></span>|<span data-ttu-id="5ce84-112">边缘</span><span class="sxs-lookup"><span data-stu-id="5ce84-112">Edge</span></span>|
|<span data-ttu-id="5ce84-113">版本</span><span class="sxs-lookup"><span data-stu-id="5ce84-113">Version</span></span>|<span data-ttu-id="5ce84-114">4.5</span><span class="sxs-lookup"><span data-stu-id="5ce84-114">4.5</span></span>|
|<span data-ttu-id="5ce84-115">类型</span><span class="sxs-lookup"><span data-stu-id="5ce84-115">Type</span></span>|<span data-ttu-id="5ce84-116">运行时</span><span class="sxs-lookup"><span data-stu-id="5ce84-116">Runtime</span></span>|
|<span data-ttu-id="5ce84-117">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="5ce84-117">Affected APIs</span></span>|<ul><li><xref:System.Xml.Xsl.XslCompiledTransform?displayProperty=nameWithType></li></ul>|
