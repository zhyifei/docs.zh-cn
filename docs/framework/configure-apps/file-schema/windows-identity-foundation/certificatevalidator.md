---
title: <certificateValidator>
ms.date: 03/30/2017
ms.assetid: 86161897-c20f-4ad8-9d7f-050c247251bf
author: BrucePerlerMS
ms.openlocfilehash: c25f183679f41f51ffee4f482bfe7a64763647d9
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69941904"
---
# <a name="certificatevalidator"></a><span data-ttu-id="88121-101">\<certificateValidator></span><span class="sxs-lookup"><span data-stu-id="88121-101">\<certificateValidator></span></span>
<span data-ttu-id="88121-102">指定证书验证的自定义类型。</span><span class="sxs-lookup"><span data-stu-id="88121-102">Specifies a custom type for certificate validation.</span></span> <span data-ttu-id="88121-103">仅当`certificateValidationMode` [ \<certificateValidation >](certificatevalidation.md)元素的属性设置为 "Custom" 时才使用此类型。</span><span class="sxs-lookup"><span data-stu-id="88121-103">This type is used only if the `certificateValidationMode` attribute of the [\<certificateValidation>](certificatevalidation.md) element is set to "Custom".</span></span>  
  
 <span data-ttu-id="88121-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="88121-104">\<system.identityModel></span></span>  
<span data-ttu-id="88121-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="88121-105">\<identityConfiguration></span></span>  
<span data-ttu-id="88121-106">\<certificateValidation></span><span class="sxs-lookup"><span data-stu-id="88121-106">\<certificateValidation></span></span>  
<span data-ttu-id="88121-107">\<certificateValidator></span><span class="sxs-lookup"><span data-stu-id="88121-107">\<certificateValidator></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="88121-108">语法</span><span class="sxs-lookup"><span data-stu-id="88121-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="88121-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="88121-109">Attributes and Elements</span></span>  
 <span data-ttu-id="88121-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="88121-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="88121-111">特性</span><span class="sxs-lookup"><span data-stu-id="88121-111">Attributes</span></span>  
  
|<span data-ttu-id="88121-112">特性</span><span class="sxs-lookup"><span data-stu-id="88121-112">Attribute</span></span>|<span data-ttu-id="88121-113">描述</span><span class="sxs-lookup"><span data-stu-id="88121-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="88121-114">type</span><span class="sxs-lookup"><span data-stu-id="88121-114">type</span></span>|<span data-ttu-id="88121-115">指定从<xref:System.IdentityModel.Selectors.X509CertificateValidator>类派生的自定义类型。</span><span class="sxs-lookup"><span data-stu-id="88121-115">Specifies a custom type that derives from the <xref:System.IdentityModel.Selectors.X509CertificateValidator> class.</span></span> <span data-ttu-id="88121-116">将 certificateValidation > 元素的`certificateValidationMode`属性[设置为 "Custom" 可\<](certificatevalidation.md)使用此类型。</span><span class="sxs-lookup"><span data-stu-id="88121-116">Set the `certificateValidationMode` attribute of the [\<certificateValidation>](certificatevalidation.md) element to "Custom" to use this type.</span></span> <span data-ttu-id="88121-117">有关如何指定`type`属性的详细信息, 请参阅[自定义类型引用](../windows-workflow-foundation/index.md)。</span><span class="sxs-lookup"><span data-stu-id="88121-117">For more information about how to specify the `type` attribute, see [Custom Type References](../windows-workflow-foundation/index.md).</span></span> <span data-ttu-id="88121-118">可选。</span><span class="sxs-lookup"><span data-stu-id="88121-118">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="88121-119">子元素</span><span class="sxs-lookup"><span data-stu-id="88121-119">Child Elements</span></span>  
 <span data-ttu-id="88121-120">无</span><span class="sxs-lookup"><span data-stu-id="88121-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="88121-121">父元素</span><span class="sxs-lookup"><span data-stu-id="88121-121">Parent Elements</span></span>  
  
|<span data-ttu-id="88121-122">元素</span><span class="sxs-lookup"><span data-stu-id="88121-122">Element</span></span>|<span data-ttu-id="88121-123">描述</span><span class="sxs-lookup"><span data-stu-id="88121-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="88121-124">\<certificateValidation></span><span class="sxs-lookup"><span data-stu-id="88121-124">\<certificateValidation></span></span>](certificatevalidation.md)|<span data-ttu-id="88121-125">控制标记处理程序用于验证证书的设置。</span><span class="sxs-lookup"><span data-stu-id="88121-125">Controls the settings that token handlers use to validate certificates.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="88121-126">示例</span><span class="sxs-lookup"><span data-stu-id="88121-126">Example</span></span>  
  
```xml  
<certificateValidation certificateValidationMode="Custom"  
                       revocationMode="Online"  
                       trustedStoreLocation="LocalMachine">  
    <certificateValidator type="MyNamespace.CustomValidator, MyAssembly" />    
</certificateValidation>        
```
