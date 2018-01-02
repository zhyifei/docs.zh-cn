---
title: '&lt;certificateValidator&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 86161897-c20f-4ad8-9d7f-050c247251bf
caps.latest.revision: "6"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 98112b3f13ff0b8e4be50f158ce40b048b213248
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ltcertificatevalidatorgt"></a><span data-ttu-id="d6855-102">&lt;certificateValidator&gt;</span><span class="sxs-lookup"><span data-stu-id="d6855-102">&lt;certificateValidator&gt;</span></span>
<span data-ttu-id="d6855-103">指定证书验证的自定义类型。</span><span class="sxs-lookup"><span data-stu-id="d6855-103">Specifies a custom type for certificate validation.</span></span> <span data-ttu-id="d6855-104">仅当使用此类型`certificateValidationMode`属性[ \<certificateValidation >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md)元素设置为"Custom"。</span><span class="sxs-lookup"><span data-stu-id="d6855-104">This type is used only if the `certificateValidationMode` attribute of the [\<certificateValidation>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md) element is set to "Custom".</span></span>  
  
 <span data-ttu-id="d6855-105">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="d6855-105">\<system.identityModel></span></span>  
<span data-ttu-id="d6855-106">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="d6855-106">\<identityConfiguration></span></span>  
<span data-ttu-id="d6855-107">\<certificateValidation ></span><span class="sxs-lookup"><span data-stu-id="d6855-107">\<certificateValidation></span></span>  
<span data-ttu-id="d6855-108">\<certificateValidator ></span><span class="sxs-lookup"><span data-stu-id="d6855-108">\<certificateValidator></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6855-109">语法</span><span class="sxs-lookup"><span data-stu-id="d6855-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d6855-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="d6855-110">Attributes and Elements</span></span>  
 <span data-ttu-id="d6855-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="d6855-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d6855-112">特性</span><span class="sxs-lookup"><span data-stu-id="d6855-112">Attributes</span></span>  
  
|<span data-ttu-id="d6855-113">特性</span><span class="sxs-lookup"><span data-stu-id="d6855-113">Attribute</span></span>|<span data-ttu-id="d6855-114">描述</span><span class="sxs-lookup"><span data-stu-id="d6855-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d6855-115">类型</span><span class="sxs-lookup"><span data-stu-id="d6855-115">type</span></span>|<span data-ttu-id="d6855-116">指定自定义类型派生自<xref:System.IdentityModel.Selectors.X509CertificateValidator>类。</span><span class="sxs-lookup"><span data-stu-id="d6855-116">Specifies a custom type that derives from the <xref:System.IdentityModel.Selectors.X509CertificateValidator> class.</span></span> <span data-ttu-id="d6855-117">设置`certificateValidationMode`属性[ \<certificateValidation >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md)为"Custom"以使用此类型的元素。</span><span class="sxs-lookup"><span data-stu-id="d6855-117">Set the `certificateValidationMode` attribute of the [\<certificateValidation>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md) element to "Custom" to use this type.</span></span> <span data-ttu-id="d6855-118">有关如何指定详细信息`type`属性，请参阅[自定义类型引用](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md)。</span><span class="sxs-lookup"><span data-stu-id="d6855-118">For more information about how to specify the `type` attribute, see [Custom Type References](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span></span> <span data-ttu-id="d6855-119">可选。</span><span class="sxs-lookup"><span data-stu-id="d6855-119">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d6855-120">子元素</span><span class="sxs-lookup"><span data-stu-id="d6855-120">Child Elements</span></span>  
 <span data-ttu-id="d6855-121">无</span><span class="sxs-lookup"><span data-stu-id="d6855-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d6855-122">父元素</span><span class="sxs-lookup"><span data-stu-id="d6855-122">Parent Elements</span></span>  
  
|<span data-ttu-id="d6855-123">元素</span><span class="sxs-lookup"><span data-stu-id="d6855-123">Element</span></span>|<span data-ttu-id="d6855-124">描述</span><span class="sxs-lookup"><span data-stu-id="d6855-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d6855-125">\<certificateValidation ></span><span class="sxs-lookup"><span data-stu-id="d6855-125">\<certificateValidation></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md)|<span data-ttu-id="d6855-126">控制令牌处理程序用来验证证书的设置。</span><span class="sxs-lookup"><span data-stu-id="d6855-126">Controls the settings that token handlers use to validate certificates.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="d6855-127">示例</span><span class="sxs-lookup"><span data-stu-id="d6855-127">Example</span></span>  
  
```xml  
<certificateValidation certificateValidationMode="Custom"  
                       revocationMode="Online"  
                       trustedStoreLocation="LocalMachine">  
    <certificateValidator type="MyNamespace.CustomValidator, MyAssembly" />    
</certificateValidation>        
```
