---
title: '&lt;certificateValidator&gt;'
ms.date: 03/30/2017
ms.assetid: 86161897-c20f-4ad8-9d7f-050c247251bf
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: a4663b0c3a2a6965a977a1d551c47de7e13d144b
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32766889"
---
# <a name="ltcertificatevalidatorgt"></a><span data-ttu-id="c0dec-102">&lt;certificateValidator&gt;</span><span class="sxs-lookup"><span data-stu-id="c0dec-102">&lt;certificateValidator&gt;</span></span>
<span data-ttu-id="c0dec-103">指定证书验证的自定义类型。</span><span class="sxs-lookup"><span data-stu-id="c0dec-103">Specifies a custom type for certificate validation.</span></span> <span data-ttu-id="c0dec-104">仅当使用此类型`certificateValidationMode`属性[ \<certificateValidation >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md)元素设置为"Custom"。</span><span class="sxs-lookup"><span data-stu-id="c0dec-104">This type is used only if the `certificateValidationMode` attribute of the [\<certificateValidation>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md) element is set to "Custom".</span></span>  
  
 <span data-ttu-id="c0dec-105">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="c0dec-105">\<system.identityModel></span></span>  
<span data-ttu-id="c0dec-106">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="c0dec-106">\<identityConfiguration></span></span>  
<span data-ttu-id="c0dec-107">\<certificateValidation ></span><span class="sxs-lookup"><span data-stu-id="c0dec-107">\<certificateValidation></span></span>  
<span data-ttu-id="c0dec-108">\<certificateValidator ></span><span class="sxs-lookup"><span data-stu-id="c0dec-108">\<certificateValidator></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0dec-109">语法</span><span class="sxs-lookup"><span data-stu-id="c0dec-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c0dec-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="c0dec-110">Attributes and Elements</span></span>  
 <span data-ttu-id="c0dec-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="c0dec-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c0dec-112">特性</span><span class="sxs-lookup"><span data-stu-id="c0dec-112">Attributes</span></span>  
  
|<span data-ttu-id="c0dec-113">特性</span><span class="sxs-lookup"><span data-stu-id="c0dec-113">Attribute</span></span>|<span data-ttu-id="c0dec-114">描述</span><span class="sxs-lookup"><span data-stu-id="c0dec-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c0dec-115">类型</span><span class="sxs-lookup"><span data-stu-id="c0dec-115">type</span></span>|<span data-ttu-id="c0dec-116">指定自定义类型派生自<xref:System.IdentityModel.Selectors.X509CertificateValidator>类。</span><span class="sxs-lookup"><span data-stu-id="c0dec-116">Specifies a custom type that derives from the <xref:System.IdentityModel.Selectors.X509CertificateValidator> class.</span></span> <span data-ttu-id="c0dec-117">设置`certificateValidationMode`属性[ \<certificateValidation >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md)为"Custom"以使用此类型的元素。</span><span class="sxs-lookup"><span data-stu-id="c0dec-117">Set the `certificateValidationMode` attribute of the [\<certificateValidation>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md) element to "Custom" to use this type.</span></span> <span data-ttu-id="c0dec-118">有关如何指定详细信息`type`属性，请参阅[自定义类型引用](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md)。</span><span class="sxs-lookup"><span data-stu-id="c0dec-118">For more information about how to specify the `type` attribute, see [Custom Type References](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span></span> <span data-ttu-id="c0dec-119">可选。</span><span class="sxs-lookup"><span data-stu-id="c0dec-119">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c0dec-120">子元素</span><span class="sxs-lookup"><span data-stu-id="c0dec-120">Child Elements</span></span>  
 <span data-ttu-id="c0dec-121">无</span><span class="sxs-lookup"><span data-stu-id="c0dec-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c0dec-122">父元素</span><span class="sxs-lookup"><span data-stu-id="c0dec-122">Parent Elements</span></span>  
  
|<span data-ttu-id="c0dec-123">元素</span><span class="sxs-lookup"><span data-stu-id="c0dec-123">Element</span></span>|<span data-ttu-id="c0dec-124">描述</span><span class="sxs-lookup"><span data-stu-id="c0dec-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c0dec-125">\<certificateValidation ></span><span class="sxs-lookup"><span data-stu-id="c0dec-125">\<certificateValidation></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md)|<span data-ttu-id="c0dec-126">控制令牌处理程序用来验证证书的设置。</span><span class="sxs-lookup"><span data-stu-id="c0dec-126">Controls the settings that token handlers use to validate certificates.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="c0dec-127">示例</span><span class="sxs-lookup"><span data-stu-id="c0dec-127">Example</span></span>  
  
```xml  
<certificateValidation certificateValidationMode="Custom"  
                       revocationMode="Online"  
                       trustedStoreLocation="LocalMachine">  
    <certificateValidator type="MyNamespace.CustomValidator, MyAssembly" />    
</certificateValidation>        
```
