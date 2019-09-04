---
title: <certificateValidator>
ms.date: 03/30/2017
ms.assetid: 86161897-c20f-4ad8-9d7f-050c247251bf
author: BrucePerlerMS
ms.openlocfilehash: 30f81dd5948a7d366c1116cffd347c85a396f5ae
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252114"
---
# <a name="certificatevalidator"></a><span data-ttu-id="071c6-101">\<certificateValidator></span><span class="sxs-lookup"><span data-stu-id="071c6-101">\<certificateValidator></span></span>
<span data-ttu-id="071c6-102">指定证书验证的自定义类型。</span><span class="sxs-lookup"><span data-stu-id="071c6-102">Specifies a custom type for certificate validation.</span></span> <span data-ttu-id="071c6-103">仅当`certificateValidationMode` [ \<certificateValidation >](certificatevalidation.md)元素的属性设置为 "Custom" 时才使用此类型。</span><span class="sxs-lookup"><span data-stu-id="071c6-103">This type is used only if the `certificateValidationMode` attribute of the [\<certificateValidation>](certificatevalidation.md) element is set to "Custom".</span></span>  
  
<span data-ttu-id="071c6-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="071c6-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="071c6-105">&nbsp;&nbsp;[ **\<System.identitymodel >** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="071c6-105">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="071c6-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<identityConfiguration >** ](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="071c6-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="071c6-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<certificateValidation >** ](certificatevalidation.md)</span><span class="sxs-lookup"><span data-stu-id="071c6-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<certificateValidation>**](certificatevalidation.md)</span></span>\
<span data-ttu-id="071c6-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<certificateValidator >**</span><span class="sxs-lookup"><span data-stu-id="071c6-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificateValidator>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="071c6-109">语法</span><span class="sxs-lookup"><span data-stu-id="071c6-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="071c6-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="071c6-110">Attributes and Elements</span></span>  
 <span data-ttu-id="071c6-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="071c6-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="071c6-112">特性</span><span class="sxs-lookup"><span data-stu-id="071c6-112">Attributes</span></span>  
  
|<span data-ttu-id="071c6-113">特性</span><span class="sxs-lookup"><span data-stu-id="071c6-113">Attribute</span></span>|<span data-ttu-id="071c6-114">描述</span><span class="sxs-lookup"><span data-stu-id="071c6-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="071c6-115">type</span><span class="sxs-lookup"><span data-stu-id="071c6-115">type</span></span>|<span data-ttu-id="071c6-116">指定从<xref:System.IdentityModel.Selectors.X509CertificateValidator>类派生的自定义类型。</span><span class="sxs-lookup"><span data-stu-id="071c6-116">Specifies a custom type that derives from the <xref:System.IdentityModel.Selectors.X509CertificateValidator> class.</span></span> <span data-ttu-id="071c6-117">将 certificateValidation > 元素的`certificateValidationMode`属性[设置为 "Custom" 可\<](certificatevalidation.md)使用此类型。</span><span class="sxs-lookup"><span data-stu-id="071c6-117">Set the `certificateValidationMode` attribute of the [\<certificateValidation>](certificatevalidation.md) element to "Custom" to use this type.</span></span> <span data-ttu-id="071c6-118">有关如何指定`type`属性的详细信息，请参阅[自定义类型引用](../windows-workflow-foundation/index.md)。</span><span class="sxs-lookup"><span data-stu-id="071c6-118">For more information about how to specify the `type` attribute, see [Custom Type References](../windows-workflow-foundation/index.md).</span></span> <span data-ttu-id="071c6-119">可选。</span><span class="sxs-lookup"><span data-stu-id="071c6-119">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="071c6-120">子元素</span><span class="sxs-lookup"><span data-stu-id="071c6-120">Child Elements</span></span>  
 <span data-ttu-id="071c6-121">无</span><span class="sxs-lookup"><span data-stu-id="071c6-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="071c6-122">父元素</span><span class="sxs-lookup"><span data-stu-id="071c6-122">Parent Elements</span></span>  
  
|<span data-ttu-id="071c6-123">元素</span><span class="sxs-lookup"><span data-stu-id="071c6-123">Element</span></span>|<span data-ttu-id="071c6-124">描述</span><span class="sxs-lookup"><span data-stu-id="071c6-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="071c6-125">\<certificateValidation></span><span class="sxs-lookup"><span data-stu-id="071c6-125">\<certificateValidation></span></span>](certificatevalidation.md)|<span data-ttu-id="071c6-126">控制标记处理程序用于验证证书的设置。</span><span class="sxs-lookup"><span data-stu-id="071c6-126">Controls the settings that token handlers use to validate certificates.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="071c6-127">示例</span><span class="sxs-lookup"><span data-stu-id="071c6-127">Example</span></span>  
  
```xml  
<certificateValidation certificateValidationMode="Custom"  
                       revocationMode="Online"  
                       trustedStoreLocation="LocalMachine">  
    <certificateValidator type="MyNamespace.CustomValidator, MyAssembly" />    
</certificateValidation>        
```
