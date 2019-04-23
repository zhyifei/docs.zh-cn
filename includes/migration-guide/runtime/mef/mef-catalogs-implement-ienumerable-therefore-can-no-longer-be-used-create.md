---
ms.openlocfilehash: 4cc91e7c6054fdb8e96cecf7120df5b9f25de56c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59803384"
---
### <a name="mef-catalogs-implement-ienumerable-and-therefore-can-no-longer-be-used-to-create-a-serializer"></a><span data-ttu-id="2893c-101">MEF 目录实现 IEnumerable，因此不能再用于创建序列化程序</span><span class="sxs-lookup"><span data-stu-id="2893c-101">MEF catalogs implement IEnumerable and therefore can no longer be used to create a serializer</span></span>

|   |   |
|---|---|
|<span data-ttu-id="2893c-102">详细信息</span><span class="sxs-lookup"><span data-stu-id="2893c-102">Details</span></span>|<span data-ttu-id="2893c-103">从 .NET Framework 4.5 开始，MEF 目录实现 IEnumerable，因此不能再用于创建序列化程序（<xref:System.Xml.Serialization.XmlSerializer?displayProperty=name> 对象）。</span><span class="sxs-lookup"><span data-stu-id="2893c-103">Starting with the .NET Framework 4.5, MEF catalogs implement IEnumerable and therefore can no longer be used to create a serializer (<xref:System.Xml.Serialization.XmlSerializer?displayProperty=name> object).</span></span> <span data-ttu-id="2893c-104">尝试对 MEF 目录进行序列化会引发异常。</span><span class="sxs-lookup"><span data-stu-id="2893c-104">Trying to serialize a MEF catalog throws an exception.</span></span>|
|<span data-ttu-id="2893c-105">建议</span><span class="sxs-lookup"><span data-stu-id="2893c-105">Suggestion</span></span>|<span data-ttu-id="2893c-106">不能再使用 MEF 创建序列化程序</span><span class="sxs-lookup"><span data-stu-id="2893c-106">Can no longer use MEF to create a serializer</span></span>|
|<span data-ttu-id="2893c-107">范围</span><span class="sxs-lookup"><span data-stu-id="2893c-107">Scope</span></span>|<span data-ttu-id="2893c-108">主要</span><span class="sxs-lookup"><span data-stu-id="2893c-108">Major</span></span>|
|<span data-ttu-id="2893c-109">版本</span><span class="sxs-lookup"><span data-stu-id="2893c-109">Version</span></span>|<span data-ttu-id="2893c-110">4.5</span><span class="sxs-lookup"><span data-stu-id="2893c-110">4.5</span></span>|
|<span data-ttu-id="2893c-111">类型</span><span class="sxs-lookup"><span data-stu-id="2893c-111">Type</span></span>|<span data-ttu-id="2893c-112">运行时</span><span class="sxs-lookup"><span data-stu-id="2893c-112">Runtime</span></span>|
