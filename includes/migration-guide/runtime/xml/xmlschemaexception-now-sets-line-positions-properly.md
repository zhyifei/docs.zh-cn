---
ms.openlocfilehash: a5b3e325c13d2f56532ebc6ebb5c259d565a4952
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "66379642"
---
### <a name="xmlschemaexception-now-sets-line-positions-properly"></a><span data-ttu-id="5307e-101">XmlSchemaException 现在正确设置行位置</span><span class="sxs-lookup"><span data-stu-id="5307e-101">XmlSchemaException now sets line positions properly</span></span>

|   |   |
|---|---|
|<span data-ttu-id="5307e-102">详细信息</span><span class="sxs-lookup"><span data-stu-id="5307e-102">Details</span></span>|<span data-ttu-id="5307e-103">如果将 <xref:System.Xml.Linq.LoadOptions.SetLineInfo> 值传递给 Load 方法并发生验证错误，则 <xref:System.Xml.Schema.XmlSchemaException.LineNumber> 和 <xref:System.Xml.Schema.XmlSchemaException.LinePosition> 属性现在包含行信息。</span><span class="sxs-lookup"><span data-stu-id="5307e-103">If the <xref:System.Xml.Linq.LoadOptions.SetLineInfo> value is passed to the Load method and a validation error occurs, the <xref:System.Xml.Schema.XmlSchemaException.LineNumber> and <xref:System.Xml.Schema.XmlSchemaException.LinePosition> properties now contain line information.</span></span>|
|<span data-ttu-id="5307e-104">建议</span><span class="sxs-lookup"><span data-stu-id="5307e-104">Suggestion</span></span>|<span data-ttu-id="5307e-105">应该更新假设不设置 <xref:System.Xml.Schema.XmlSchemaException.LineNumber> 和 <xref:System.Xml.Schema.XmlSchemaException.LinePosition> 的异常处理代码，因为这些属性将会在加载 XML 且使用 SetLineInfo 的时候正确设置。</span><span class="sxs-lookup"><span data-stu-id="5307e-105">Exception-handling code that assumes <xref:System.Xml.Schema.XmlSchemaException.LineNumber> and <xref:System.Xml.Schema.XmlSchemaException.LinePosition> will not be set should be updated since these properties will now be set properly when SetLineInfo is used while loading XML.</span></span>|
|<span data-ttu-id="5307e-106">范围</span><span class="sxs-lookup"><span data-stu-id="5307e-106">Scope</span></span>|<span data-ttu-id="5307e-107">边缘</span><span class="sxs-lookup"><span data-stu-id="5307e-107">Edge</span></span>|
|<span data-ttu-id="5307e-108">版本</span><span class="sxs-lookup"><span data-stu-id="5307e-108">Version</span></span>|<span data-ttu-id="5307e-109">4.5</span><span class="sxs-lookup"><span data-stu-id="5307e-109">4.5</span></span>|
|<span data-ttu-id="5307e-110">类型</span><span class="sxs-lookup"><span data-stu-id="5307e-110">Type</span></span>|<span data-ttu-id="5307e-111">运行时</span><span class="sxs-lookup"><span data-stu-id="5307e-111">Runtime</span></span>|
|<span data-ttu-id="5307e-112">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="5307e-112">Affected APIs</span></span>|<ul><li><xref:System.Xml.Linq.LoadOptions.SetLineInfo?displayProperty=nameWithType></li></ul>|
