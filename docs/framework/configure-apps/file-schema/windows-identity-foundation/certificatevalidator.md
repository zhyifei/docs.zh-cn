---
title: <certificateValidator>
ms.date: 03/30/2017
ms.assetid: 86161897-c20f-4ad8-9d7f-050c247251bf
author: BrucePerlerMS
ms.openlocfilehash: df52212305e0865b8c03fdd49068cb7c7da4fa38
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2019
ms.locfileid: "55277442"
---
# <a name="certificatevalidator"></a><span data-ttu-id="5dcce-101">\<certificateValidator></span><span class="sxs-lookup"><span data-stu-id="5dcce-101">\<certificateValidator></span></span>
<span data-ttu-id="5dcce-102">指定证书验证的自定义类型。</span><span class="sxs-lookup"><span data-stu-id="5dcce-102">Specifies a custom type for certificate validation.</span></span> <span data-ttu-id="5dcce-103">仅当使用此类型`certificateValidationMode`的属性[ \<certificatevalidation 设置 >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md)元素设置为"自定义"。</span><span class="sxs-lookup"><span data-stu-id="5dcce-103">This type is used only if the `certificateValidationMode` attribute of the [\<certificateValidation>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md) element is set to "Custom".</span></span>  
  
 <span data-ttu-id="5dcce-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="5dcce-104">\<system.identityModel></span></span>  
<span data-ttu-id="5dcce-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="5dcce-105">\<identityConfiguration></span></span>  
<span data-ttu-id="5dcce-106">\<certificateValidation></span><span class="sxs-lookup"><span data-stu-id="5dcce-106">\<certificateValidation></span></span>  
<span data-ttu-id="5dcce-107">\<certificateValidator></span><span class="sxs-lookup"><span data-stu-id="5dcce-107">\<certificateValidator></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5dcce-108">语法</span><span class="sxs-lookup"><span data-stu-id="5dcce-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5dcce-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="5dcce-109">Attributes and Elements</span></span>  
 <span data-ttu-id="5dcce-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="5dcce-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5dcce-111">特性</span><span class="sxs-lookup"><span data-stu-id="5dcce-111">Attributes</span></span>  
  
|<span data-ttu-id="5dcce-112">特性</span><span class="sxs-lookup"><span data-stu-id="5dcce-112">Attribute</span></span>|<span data-ttu-id="5dcce-113">描述</span><span class="sxs-lookup"><span data-stu-id="5dcce-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5dcce-114">类型</span><span class="sxs-lookup"><span data-stu-id="5dcce-114">type</span></span>|<span data-ttu-id="5dcce-115">指定派生的自定义类型<xref:System.IdentityModel.Selectors.X509CertificateValidator>类。</span><span class="sxs-lookup"><span data-stu-id="5dcce-115">Specifies a custom type that derives from the <xref:System.IdentityModel.Selectors.X509CertificateValidator> class.</span></span> <span data-ttu-id="5dcce-116">设置`certificateValidationMode`的属性[ \<certificatevalidation 设置 >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md)为"Custom"要使用此类型的元素。</span><span class="sxs-lookup"><span data-stu-id="5dcce-116">Set the `certificateValidationMode` attribute of the [\<certificateValidation>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md) element to "Custom" to use this type.</span></span> <span data-ttu-id="5dcce-117">有关如何指定详细信息`type`属性，请参阅[自定义类型引用](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md)。</span><span class="sxs-lookup"><span data-stu-id="5dcce-117">For more information about how to specify the `type` attribute, see [Custom Type References](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span></span> <span data-ttu-id="5dcce-118">可选。</span><span class="sxs-lookup"><span data-stu-id="5dcce-118">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5dcce-119">子元素</span><span class="sxs-lookup"><span data-stu-id="5dcce-119">Child Elements</span></span>  
 <span data-ttu-id="5dcce-120">无</span><span class="sxs-lookup"><span data-stu-id="5dcce-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5dcce-121">父元素</span><span class="sxs-lookup"><span data-stu-id="5dcce-121">Parent Elements</span></span>  
  
|<span data-ttu-id="5dcce-122">元素</span><span class="sxs-lookup"><span data-stu-id="5dcce-122">Element</span></span>|<span data-ttu-id="5dcce-123">描述</span><span class="sxs-lookup"><span data-stu-id="5dcce-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5dcce-124">\<certificateValidation></span><span class="sxs-lookup"><span data-stu-id="5dcce-124">\<certificateValidation></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md)|<span data-ttu-id="5dcce-125">控制令牌处理程序用来验证证书的设置。</span><span class="sxs-lookup"><span data-stu-id="5dcce-125">Controls the settings that token handlers use to validate certificates.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="5dcce-126">示例</span><span class="sxs-lookup"><span data-stu-id="5dcce-126">Example</span></span>  
  
```xml  
<certificateValidation certificateValidationMode="Custom"  
                       revocationMode="Online"  
                       trustedStoreLocation="LocalMachine">  
    <certificateValidator type="MyNamespace.CustomValidator, MyAssembly" />    
</certificateValidation>        
```
