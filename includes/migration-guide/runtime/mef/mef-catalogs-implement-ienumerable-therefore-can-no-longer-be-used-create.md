---
ms.openlocfilehash: 4cc91e7c6054fdb8e96cecf7120df5b9f25de56c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235161"
---
### <a name="mef-catalogs-implement-ienumerable-and-therefore-can-no-longer-be-used-to-create-a-serializer"></a><span data-ttu-id="37516-101">MEF 目录实现 IEnumerable，因此不能再用于创建序列化程序</span><span class="sxs-lookup"><span data-stu-id="37516-101">MEF catalogs implement IEnumerable and therefore can no longer be used to create a serializer</span></span>

|   |   |
|---|---|
|<span data-ttu-id="37516-102">详细信息</span><span class="sxs-lookup"><span data-stu-id="37516-102">Details</span></span>|<span data-ttu-id="37516-103">从 .NET Framework 4.5 开始，MEF 目录实现 IEnumerable，因此不能再用于创建序列化程序（<xref:System.Xml.Serialization.XmlSerializer?displayProperty=name> 对象）。</span><span class="sxs-lookup"><span data-stu-id="37516-103">Starting with the .NET Framework 4.5, MEF catalogs implement IEnumerable and therefore can no longer be used to create a serializer (<xref:System.Xml.Serialization.XmlSerializer?displayProperty=name> object).</span></span> <span data-ttu-id="37516-104">尝试对 MEF 目录进行序列化会引发异常。</span><span class="sxs-lookup"><span data-stu-id="37516-104">Trying to serialize a MEF catalog throws an exception.</span></span>|
|<span data-ttu-id="37516-105">建议</span><span class="sxs-lookup"><span data-stu-id="37516-105">Suggestion</span></span>|<span data-ttu-id="37516-106">不能再使用 MEF 创建序列化程序</span><span class="sxs-lookup"><span data-stu-id="37516-106">Can no longer use MEF to create a serializer</span></span>|
|<span data-ttu-id="37516-107">范围</span><span class="sxs-lookup"><span data-stu-id="37516-107">Scope</span></span>|<span data-ttu-id="37516-108">主要</span><span class="sxs-lookup"><span data-stu-id="37516-108">Major</span></span>|
|<span data-ttu-id="37516-109">版本</span><span class="sxs-lookup"><span data-stu-id="37516-109">Version</span></span>|<span data-ttu-id="37516-110">4.5</span><span class="sxs-lookup"><span data-stu-id="37516-110">4.5</span></span>|
|<span data-ttu-id="37516-111">类型</span><span class="sxs-lookup"><span data-stu-id="37516-111">Type</span></span>|<span data-ttu-id="37516-112">运行时</span><span class="sxs-lookup"><span data-stu-id="37516-112">Runtime</span></span>|
