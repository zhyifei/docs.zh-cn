---
title: '&lt;certificateValidator&gt;'
ms.date: 03/30/2017
ms.assetid: 86161897-c20f-4ad8-9d7f-050c247251bf
author: BrucePerlerMS
ms.openlocfilehash: 65b8aa6fa4422579ce0d1c5e33d3418ea051612a
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/26/2018
ms.locfileid: "47236775"
---
# <a name="ltcertificatevalidatorgt"></a><span data-ttu-id="f52f9-102">&lt;certificateValidator&gt;</span><span class="sxs-lookup"><span data-stu-id="f52f9-102">&lt;certificateValidator&gt;</span></span>
<span data-ttu-id="f52f9-103">指定证书验证的自定义类型。</span><span class="sxs-lookup"><span data-stu-id="f52f9-103">Specifies a custom type for certificate validation.</span></span> <span data-ttu-id="f52f9-104">仅当使用此类型`certificateValidationMode`的属性[ \<certificatevalidation 设置 >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md)元素设置为"自定义"。</span><span class="sxs-lookup"><span data-stu-id="f52f9-104">This type is used only if the `certificateValidationMode` attribute of the [\<certificateValidation>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md) element is set to "Custom".</span></span>  
  
 <span data-ttu-id="f52f9-105">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="f52f9-105">\<system.identityModel></span></span>  
<span data-ttu-id="f52f9-106">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="f52f9-106">\<identityConfiguration></span></span>  
<span data-ttu-id="f52f9-107">\<certificatevalidation 设置 ></span><span class="sxs-lookup"><span data-stu-id="f52f9-107">\<certificateValidation></span></span>  
<span data-ttu-id="f52f9-108">\<certificateValidator ></span><span class="sxs-lookup"><span data-stu-id="f52f9-108">\<certificateValidator></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f52f9-109">语法</span><span class="sxs-lookup"><span data-stu-id="f52f9-109">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <certificateValidation>  
      <certificateValidator type=xs:string>  
      </certificateValidator>  
    </certificateValidation>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f52f9-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="f52f9-110">Attributes and Elements</span></span>  
 <span data-ttu-id="f52f9-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="f52f9-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f52f9-112">特性</span><span class="sxs-lookup"><span data-stu-id="f52f9-112">Attributes</span></span>  
  
|<span data-ttu-id="f52f9-113">特性</span><span class="sxs-lookup"><span data-stu-id="f52f9-113">Attribute</span></span>|<span data-ttu-id="f52f9-114">描述</span><span class="sxs-lookup"><span data-stu-id="f52f9-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f52f9-115">类型</span><span class="sxs-lookup"><span data-stu-id="f52f9-115">type</span></span>|<span data-ttu-id="f52f9-116">指定派生的自定义类型<xref:System.IdentityModel.Selectors.X509CertificateValidator>类。</span><span class="sxs-lookup"><span data-stu-id="f52f9-116">Specifies a custom type that derives from the <xref:System.IdentityModel.Selectors.X509CertificateValidator> class.</span></span> <span data-ttu-id="f52f9-117">设置`certificateValidationMode`的属性[ \<certificatevalidation 设置 >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md)为"Custom"要使用此类型的元素。</span><span class="sxs-lookup"><span data-stu-id="f52f9-117">Set the `certificateValidationMode` attribute of the [\<certificateValidation>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md) element to "Custom" to use this type.</span></span> <span data-ttu-id="f52f9-118">有关如何指定详细信息`type`属性，请参阅[自定义类型引用](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md)。</span><span class="sxs-lookup"><span data-stu-id="f52f9-118">For more information about how to specify the `type` attribute, see [Custom Type References](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span></span> <span data-ttu-id="f52f9-119">可选。</span><span class="sxs-lookup"><span data-stu-id="f52f9-119">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f52f9-120">子元素</span><span class="sxs-lookup"><span data-stu-id="f52f9-120">Child Elements</span></span>  
 <span data-ttu-id="f52f9-121">无</span><span class="sxs-lookup"><span data-stu-id="f52f9-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f52f9-122">父元素</span><span class="sxs-lookup"><span data-stu-id="f52f9-122">Parent Elements</span></span>  
  
|<span data-ttu-id="f52f9-123">元素</span><span class="sxs-lookup"><span data-stu-id="f52f9-123">Element</span></span>|<span data-ttu-id="f52f9-124">描述</span><span class="sxs-lookup"><span data-stu-id="f52f9-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f52f9-125">\<certificatevalidation 设置 ></span><span class="sxs-lookup"><span data-stu-id="f52f9-125">\<certificateValidation></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md)|<span data-ttu-id="f52f9-126">控制令牌处理程序用来验证证书的设置。</span><span class="sxs-lookup"><span data-stu-id="f52f9-126">Controls the settings that token handlers use to validate certificates.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="f52f9-127">示例</span><span class="sxs-lookup"><span data-stu-id="f52f9-127">Example</span></span>  
  
```xml  
<certificateValidation certificateValidationMode="Custom"  
                       revocationMode="Online"  
                       trustedStoreLocation="LocalMachine">  
    <certificateValidator type="MyNamespace.CustomValidator, MyAssembly" />    
</certificateValidation>        
```
