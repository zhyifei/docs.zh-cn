---
title: XmlDictionaryReaderQuotas
ms.date: 03/30/2017
ms.assetid: 9b4ca8b4-0a89-4758-97ab-528a8ce18f07
ms.openlocfilehash: f1c12a0a60397a84d4e9ff0241c4182b4511af5c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59767703"
---
# <a name="xmldictionaryreaderquotas"></a><span data-ttu-id="3ef42-102">XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="3ef42-102">XmlDictionaryReaderQuotas</span></span>
<span data-ttu-id="3ef42-103">XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="3ef42-103">XmlDictionaryReaderQuotas</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ef42-104">语法</span><span class="sxs-lookup"><span data-stu-id="3ef42-104">Syntax</span></span>  
  
```csharp
class XmlDictionaryReaderQuotas  
{  
  sint32 MaxArrayLength;  
  sint32 MaxBytesPerRead;  
  sint32 MaxDepth;  
  sint32 MaxNameTableCharCount;  
  sint32 MaxStringContentLength;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="3ef42-105">方法</span><span class="sxs-lookup"><span data-stu-id="3ef42-105">Methods</span></span>  
 <span data-ttu-id="3ef42-106">XmlDictionaryReaderQuotas 类不定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="3ef42-106">The XmlDictionaryReaderQuotas class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="3ef42-107">属性</span><span class="sxs-lookup"><span data-stu-id="3ef42-107">Properties</span></span>  
 <span data-ttu-id="3ef42-108">XmlDictionaryReaderQuotas 类具有以下属性：</span><span class="sxs-lookup"><span data-stu-id="3ef42-108">The XmlDictionaryReaderQuotas class has the following properties:</span></span>  
  
### <a name="maxarraylength"></a><span data-ttu-id="3ef42-109">MaxArrayLength</span><span class="sxs-lookup"><span data-stu-id="3ef42-109">MaxArrayLength</span></span>  
 <span data-ttu-id="3ef42-110">数据类型：sint32</span><span class="sxs-lookup"><span data-stu-id="3ef42-110">Data type: sint32</span></span>  
  
 <span data-ttu-id="3ef42-111">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="3ef42-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3ef42-112">允许的最大数组长度。</span><span class="sxs-lookup"><span data-stu-id="3ef42-112">The maximum allowed array length.</span></span>  
  
### <a name="maxbytesperread"></a><span data-ttu-id="3ef42-113">MaxBytesPerRead</span><span class="sxs-lookup"><span data-stu-id="3ef42-113">MaxBytesPerRead</span></span>  
 <span data-ttu-id="3ef42-114">数据类型：sint32</span><span class="sxs-lookup"><span data-stu-id="3ef42-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="3ef42-115">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="3ef42-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3ef42-116">允许为每次读取返回的最大字节数。</span><span class="sxs-lookup"><span data-stu-id="3ef42-116">The maximum allowed bytes returned for each read.</span></span>  
  
### <a name="maxdepth"></a><span data-ttu-id="3ef42-117">MaxDepth</span><span class="sxs-lookup"><span data-stu-id="3ef42-117">MaxDepth</span></span>  
 <span data-ttu-id="3ef42-118">数据类型：sint32</span><span class="sxs-lookup"><span data-stu-id="3ef42-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="3ef42-119">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="3ef42-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3ef42-120">每次读取的最大嵌套节点深度。</span><span class="sxs-lookup"><span data-stu-id="3ef42-120">The maximum nested node depth for each read.</span></span>  
  
### <a name="maxnametablecharcount"></a><span data-ttu-id="3ef42-121">MaxNameTableCharCount</span><span class="sxs-lookup"><span data-stu-id="3ef42-121">MaxNameTableCharCount</span></span>  
 <span data-ttu-id="3ef42-122">数据类型：sint32</span><span class="sxs-lookup"><span data-stu-id="3ef42-122">Data type: sint32</span></span>  
  
 <span data-ttu-id="3ef42-123">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="3ef42-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3ef42-124">表名称中允许的最大字符数。</span><span class="sxs-lookup"><span data-stu-id="3ef42-124">The maximum characters allowed in a table name.</span></span>  
  
### <a name="maxstringcontentlength"></a><span data-ttu-id="3ef42-125">MaxStringContentLength</span><span class="sxs-lookup"><span data-stu-id="3ef42-125">MaxStringContentLength</span></span>  
 <span data-ttu-id="3ef42-126">数据类型：sint32</span><span class="sxs-lookup"><span data-stu-id="3ef42-126">Data type: sint32</span></span>  
  
 <span data-ttu-id="3ef42-127">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="3ef42-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3ef42-128">XML 元素内容中允许包含的最大字符数。</span><span class="sxs-lookup"><span data-stu-id="3ef42-128">The maximum characters allowed in XML element content.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3ef42-129">要求</span><span class="sxs-lookup"><span data-stu-id="3ef42-129">Requirements</span></span>  
  
|<span data-ttu-id="3ef42-130">MOF</span><span class="sxs-lookup"><span data-stu-id="3ef42-130">MOF</span></span>|<span data-ttu-id="3ef42-131">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="3ef42-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="3ef42-132">命名空间</span><span class="sxs-lookup"><span data-stu-id="3ef42-132">Namespace</span></span>|<span data-ttu-id="3ef42-133">已在 root\ServiceModel 中定义</span><span class="sxs-lookup"><span data-stu-id="3ef42-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3ef42-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="3ef42-134">See also</span></span>

- <xref:System.Xml.XmlDictionaryReaderQuotas>
- <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>
