---
title: XmlDictionaryReaderQuotas
ms.date: 03/30/2017
ms.assetid: 9b4ca8b4-0a89-4758-97ab-528a8ce18f07
ms.openlocfilehash: 78914d52a9e57fe2e48adcfc0d7b6f911a0d8b3a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33487823"
---
# <a name="xmldictionaryreaderquotas"></a><span data-ttu-id="f6eb9-102">XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="f6eb9-102">XmlDictionaryReaderQuotas</span></span>
<span data-ttu-id="f6eb9-103">XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="f6eb9-103">XmlDictionaryReaderQuotas</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6eb9-104">语法</span><span class="sxs-lookup"><span data-stu-id="f6eb9-104">Syntax</span></span>  
  
```  
class XmlDictionaryReaderQuotas  
{  
  sint32 MaxArrayLength;  
  sint32 MaxBytesPerRead;  
  sint32 MaxDepth;  
  sint32 MaxNameTableCharCount;  
  sint32 MaxStringContentLength;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="f6eb9-105">方法</span><span class="sxs-lookup"><span data-stu-id="f6eb9-105">Methods</span></span>  
 <span data-ttu-id="f6eb9-106">XmlDictionaryReaderQuotas 类不定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="f6eb9-106">The XmlDictionaryReaderQuotas class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="f6eb9-107">属性</span><span class="sxs-lookup"><span data-stu-id="f6eb9-107">Properties</span></span>  
 <span data-ttu-id="f6eb9-108">XmlDictionaryReaderQuotas 类具有以下属性：</span><span class="sxs-lookup"><span data-stu-id="f6eb9-108">The XmlDictionaryReaderQuotas class has the following properties:</span></span>  
  
### <a name="maxarraylength"></a><span data-ttu-id="f6eb9-109">MaxArrayLength</span><span class="sxs-lookup"><span data-stu-id="f6eb9-109">MaxArrayLength</span></span>  
 <span data-ttu-id="f6eb9-110">数据类型：sint32</span><span class="sxs-lookup"><span data-stu-id="f6eb9-110">Data type: sint32</span></span>  
  
 <span data-ttu-id="f6eb9-111">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="f6eb9-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f6eb9-112">允许的最大数组长度。</span><span class="sxs-lookup"><span data-stu-id="f6eb9-112">The maximum allowed array length.</span></span>  
  
### <a name="maxbytesperread"></a><span data-ttu-id="f6eb9-113">MaxBytesPerRead</span><span class="sxs-lookup"><span data-stu-id="f6eb9-113">MaxBytesPerRead</span></span>  
 <span data-ttu-id="f6eb9-114">数据类型：sint32</span><span class="sxs-lookup"><span data-stu-id="f6eb9-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="f6eb9-115">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="f6eb9-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f6eb9-116">允许为每次读取返回的最大字节数。</span><span class="sxs-lookup"><span data-stu-id="f6eb9-116">The maximum allowed bytes returned for each read.</span></span>  
  
### <a name="maxdepth"></a><span data-ttu-id="f6eb9-117">MaxDepth</span><span class="sxs-lookup"><span data-stu-id="f6eb9-117">MaxDepth</span></span>  
 <span data-ttu-id="f6eb9-118">数据类型：sint32</span><span class="sxs-lookup"><span data-stu-id="f6eb9-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="f6eb9-119">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="f6eb9-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f6eb9-120">每次读取的最大嵌套节点深度。</span><span class="sxs-lookup"><span data-stu-id="f6eb9-120">The maximum nested node depth for each read.</span></span>  
  
### <a name="maxnametablecharcount"></a><span data-ttu-id="f6eb9-121">MaxNameTableCharCount</span><span class="sxs-lookup"><span data-stu-id="f6eb9-121">MaxNameTableCharCount</span></span>  
 <span data-ttu-id="f6eb9-122">数据类型：sint32</span><span class="sxs-lookup"><span data-stu-id="f6eb9-122">Data type: sint32</span></span>  
  
 <span data-ttu-id="f6eb9-123">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="f6eb9-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f6eb9-124">表名称中允许的最大字符数。</span><span class="sxs-lookup"><span data-stu-id="f6eb9-124">The maximum characters allowed in a table name.</span></span>  
  
### <a name="maxstringcontentlength"></a><span data-ttu-id="f6eb9-125">MaxStringContentLength</span><span class="sxs-lookup"><span data-stu-id="f6eb9-125">MaxStringContentLength</span></span>  
 <span data-ttu-id="f6eb9-126">数据类型：sint32</span><span class="sxs-lookup"><span data-stu-id="f6eb9-126">Data type: sint32</span></span>  
  
 <span data-ttu-id="f6eb9-127">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="f6eb9-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f6eb9-128">XML 元素内容中允许包含的最大字符数。</span><span class="sxs-lookup"><span data-stu-id="f6eb9-128">The maximum characters allowed in XML element content.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f6eb9-129">要求</span><span class="sxs-lookup"><span data-stu-id="f6eb9-129">Requirements</span></span>  
  
|<span data-ttu-id="f6eb9-130">MOF</span><span class="sxs-lookup"><span data-stu-id="f6eb9-130">MOF</span></span>|<span data-ttu-id="f6eb9-131">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="f6eb9-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="f6eb9-132">命名空间</span><span class="sxs-lookup"><span data-stu-id="f6eb9-132">Namespace</span></span>|<span data-ttu-id="f6eb9-133">已在 root\ServiceModel 中定义</span><span class="sxs-lookup"><span data-stu-id="f6eb9-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f6eb9-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="f6eb9-134">See Also</span></span>  
 <xref:System.Xml.XmlDictionaryReaderQuotas>  
 <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>
