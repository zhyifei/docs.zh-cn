---
title: <certificateValidator>
ms.date: 03/30/2017
ms.assetid: 86161897-c20f-4ad8-9d7f-050c247251bf
author: BrucePerlerMS
ms.openlocfilehash: df52212305e0865b8c03fdd49068cb7c7da4fa38
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61667361"
---
# <a name="certificatevalidator"></a><span data-ttu-id="851b5-101">\<certificateValidator></span><span class="sxs-lookup"><span data-stu-id="851b5-101">\<certificateValidator></span></span>
<span data-ttu-id="851b5-102">指定证书验证的自定义类型。</span><span class="sxs-lookup"><span data-stu-id="851b5-102">Specifies a custom type for certificate validation.</span></span> <span data-ttu-id="851b5-103">仅当使用此类型`certificateValidationMode`的属性[ \<certificatevalidation 设置 >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md)元素设置为"自定义"。</span><span class="sxs-lookup"><span data-stu-id="851b5-103">This type is used only if the `certificateValidationMode` attribute of the [\<certificateValidation>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md) element is set to "Custom".</span></span>  
  
 <span data-ttu-id="851b5-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="851b5-104">\<system.identityModel></span></span>  
<span data-ttu-id="851b5-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="851b5-105">\<identityConfiguration></span></span>  
<span data-ttu-id="851b5-106">\<certificateValidation></span><span class="sxs-lookup"><span data-stu-id="851b5-106">\<certificateValidation></span></span>  
<span data-ttu-id="851b5-107">\<certificateValidator></span><span class="sxs-lookup"><span data-stu-id="851b5-107">\<certificateValidator></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="851b5-108">语法</span><span class="sxs-lookup"><span data-stu-id="851b5-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="851b5-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="851b5-109">Attributes and Elements</span></span>  
 <span data-ttu-id="851b5-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="851b5-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="851b5-111">特性</span><span class="sxs-lookup"><span data-stu-id="851b5-111">Attributes</span></span>  
  
|<span data-ttu-id="851b5-112">特性</span><span class="sxs-lookup"><span data-stu-id="851b5-112">Attribute</span></span>|<span data-ttu-id="851b5-113">描述</span><span class="sxs-lookup"><span data-stu-id="851b5-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="851b5-114">类型</span><span class="sxs-lookup"><span data-stu-id="851b5-114">type</span></span>|<span data-ttu-id="851b5-115">指定派生的自定义类型<xref:System.IdentityModel.Selectors.X509CertificateValidator>类。</span><span class="sxs-lookup"><span data-stu-id="851b5-115">Specifies a custom type that derives from the <xref:System.IdentityModel.Selectors.X509CertificateValidator> class.</span></span> <span data-ttu-id="851b5-116">设置`certificateValidationMode`的属性[ \<certificatevalidation 设置 >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md)为"Custom"要使用此类型的元素。</span><span class="sxs-lookup"><span data-stu-id="851b5-116">Set the `certificateValidationMode` attribute of the [\<certificateValidation>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md) element to "Custom" to use this type.</span></span> <span data-ttu-id="851b5-117">有关如何指定详细信息`type`属性，请参阅[自定义类型引用](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md)。</span><span class="sxs-lookup"><span data-stu-id="851b5-117">For more information about how to specify the `type` attribute, see [Custom Type References](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span></span> <span data-ttu-id="851b5-118">可选。</span><span class="sxs-lookup"><span data-stu-id="851b5-118">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="851b5-119">子元素</span><span class="sxs-lookup"><span data-stu-id="851b5-119">Child Elements</span></span>  
 <span data-ttu-id="851b5-120">None</span><span class="sxs-lookup"><span data-stu-id="851b5-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="851b5-121">父元素</span><span class="sxs-lookup"><span data-stu-id="851b5-121">Parent Elements</span></span>  
  
|<span data-ttu-id="851b5-122">元素</span><span class="sxs-lookup"><span data-stu-id="851b5-122">Element</span></span>|<span data-ttu-id="851b5-123">描述</span><span class="sxs-lookup"><span data-stu-id="851b5-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="851b5-124">\<certificateValidation></span><span class="sxs-lookup"><span data-stu-id="851b5-124">\<certificateValidation></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md)|<span data-ttu-id="851b5-125">控制令牌处理程序用来验证证书的设置。</span><span class="sxs-lookup"><span data-stu-id="851b5-125">Controls the settings that token handlers use to validate certificates.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="851b5-126">示例</span><span class="sxs-lookup"><span data-stu-id="851b5-126">Example</span></span>  
  
```xml  
<certificateValidation certificateValidationMode="Custom"  
                       revocationMode="Online"  
                       trustedStoreLocation="LocalMachine">  
    <certificateValidator type="MyNamespace.CustomValidator, MyAssembly" />    
</certificateValidation>        
```
