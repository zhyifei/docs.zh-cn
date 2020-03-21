---
title: <certificateValidator>
ms.date: 03/30/2017
ms.assetid: 86161897-c20f-4ad8-9d7f-050c247251bf
author: BrucePerlerMS
ms.openlocfilehash: 3f3d79d3567c1714a79423b7767ce3f454b9d52d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152783"
---
# <a name="certificatevalidator"></a><span data-ttu-id="a25f0-101">\<证书验证器></span><span class="sxs-lookup"><span data-stu-id="a25f0-101">\<certificateValidator></span></span>
<span data-ttu-id="a25f0-102">指定证书验证的自定义类型。</span><span class="sxs-lookup"><span data-stu-id="a25f0-102">Specifies a custom type for certificate validation.</span></span> <span data-ttu-id="a25f0-103">`certificateValidationMode`[仅当\<证书验证>](certificatevalidation.md)元素的属性设置为"自定义"时，才使用此类型。</span><span class="sxs-lookup"><span data-stu-id="a25f0-103">This type is used only if the `certificateValidationMode` attribute of the [\<certificateValidation>](certificatevalidation.md) element is set to "Custom".</span></span>  
  
<span data-ttu-id="a25f0-104">[**\<配置>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="a25f0-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="a25f0-105">&nbsp;&nbsp;[**\<系统.身份模型>**](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="a25f0-105">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="a25f0-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<身份配置>**](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="a25f0-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="a25f0-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<证书验证>**](certificatevalidation.md)</span><span class="sxs-lookup"><span data-stu-id="a25f0-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<certificateValidation>**](certificatevalidation.md)</span></span>\
<span data-ttu-id="a25f0-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<证书验证器>**</span><span class="sxs-lookup"><span data-stu-id="a25f0-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificateValidator>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a25f0-109">语法</span><span class="sxs-lookup"><span data-stu-id="a25f0-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a25f0-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="a25f0-110">Attributes and Elements</span></span>  
 <span data-ttu-id="a25f0-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="a25f0-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a25f0-112">属性</span><span class="sxs-lookup"><span data-stu-id="a25f0-112">Attributes</span></span>  
  
|<span data-ttu-id="a25f0-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="a25f0-113">Attribute</span></span>|<span data-ttu-id="a25f0-114">说明</span><span class="sxs-lookup"><span data-stu-id="a25f0-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a25f0-115">type</span><span class="sxs-lookup"><span data-stu-id="a25f0-115">type</span></span>|<span data-ttu-id="a25f0-116">指定派生自类的<xref:System.IdentityModel.Selectors.X509CertificateValidator>自定义类型。</span><span class="sxs-lookup"><span data-stu-id="a25f0-116">Specifies a custom type that derives from the <xref:System.IdentityModel.Selectors.X509CertificateValidator> class.</span></span> <span data-ttu-id="a25f0-117">`certificateValidationMode`[将\<证书验证>](certificatevalidation.md)元素的属性设置为"自定义"以使用此类型。</span><span class="sxs-lookup"><span data-stu-id="a25f0-117">Set the `certificateValidationMode` attribute of the [\<certificateValidation>](certificatevalidation.md) element to "Custom" to use this type.</span></span> <span data-ttu-id="a25f0-118">有关如何指定属性的详细信息，`type`请参阅[自定义类型引用](../windows-workflow-foundation/index.md)。</span><span class="sxs-lookup"><span data-stu-id="a25f0-118">For more information about how to specify the `type` attribute, see [Custom Type References](../windows-workflow-foundation/index.md).</span></span> <span data-ttu-id="a25f0-119">可选。</span><span class="sxs-lookup"><span data-stu-id="a25f0-119">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a25f0-120">子元素</span><span class="sxs-lookup"><span data-stu-id="a25f0-120">Child Elements</span></span>  
 <span data-ttu-id="a25f0-121">无</span><span class="sxs-lookup"><span data-stu-id="a25f0-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a25f0-122">父元素</span><span class="sxs-lookup"><span data-stu-id="a25f0-122">Parent Elements</span></span>  
  
|<span data-ttu-id="a25f0-123">元素</span><span class="sxs-lookup"><span data-stu-id="a25f0-123">Element</span></span>|<span data-ttu-id="a25f0-124">说明</span><span class="sxs-lookup"><span data-stu-id="a25f0-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a25f0-125">\<证书验证></span><span class="sxs-lookup"><span data-stu-id="a25f0-125">\<certificateValidation></span></span>](certificatevalidation.md)|<span data-ttu-id="a25f0-126">控制令牌处理程序用于验证证书的设置。</span><span class="sxs-lookup"><span data-stu-id="a25f0-126">Controls the settings that token handlers use to validate certificates.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="a25f0-127">示例</span><span class="sxs-lookup"><span data-stu-id="a25f0-127">Example</span></span>  
  
```xml  
<certificateValidation certificateValidationMode="Custom"  
                       revocationMode="Online"  
                       trustedStoreLocation="LocalMachine">  
    <certificateValidator type="MyNamespace.CustomValidator, MyAssembly" />
</certificateValidation>
```
