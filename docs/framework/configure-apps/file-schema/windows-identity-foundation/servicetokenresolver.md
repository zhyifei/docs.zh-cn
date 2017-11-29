---
title: '&lt;serviceTokenResolver&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6e9001e1-e064-4f47-84b2-46225c177746
caps.latest.revision: "8"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 06e871ee31880a219d9105ff4ce667618bfb78f0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="ltservicetokenresolvergt"></a><span data-ttu-id="fcc98-102">&lt;serviceTokenResolver&gt;</span><span class="sxs-lookup"><span data-stu-id="fcc98-102">&lt;serviceTokenResolver&gt;</span></span>
<span data-ttu-id="fcc98-103">注册的服务令牌解析程序由标记处理程序集合中的处理程序。</span><span class="sxs-lookup"><span data-stu-id="fcc98-103">Registers the service token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="fcc98-104">服务的标记解析程序用于解析在传入令牌和消息上的加密令牌。</span><span class="sxs-lookup"><span data-stu-id="fcc98-104">The service token resolver is used to resolve the encryption token on incoming tokens and messages.</span></span>  
  
 <span data-ttu-id="fcc98-105">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="fcc98-105">\<system.identityModel></span></span>  
<span data-ttu-id="fcc98-106">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="fcc98-106">\<identityConfiguration></span></span>  
<span data-ttu-id="fcc98-107">\<securityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="fcc98-107">\<securityTokenHandlers></span></span>  
<span data-ttu-id="fcc98-108">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="fcc98-108">\<securityTokenHandlerConfiguration></span></span>  
<span data-ttu-id="fcc98-109">\<serviceTokenResolver ></span><span class="sxs-lookup"><span data-stu-id="fcc98-109">\<serviceTokenResolver></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fcc98-110">语法</span><span class="sxs-lookup"><span data-stu-id="fcc98-110">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration>  
        <serviceTokenResolver type=xs:string>  
        </serviceTokenResolver>  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fcc98-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="fcc98-111">Attributes and Elements</span></span>  
 <span data-ttu-id="fcc98-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="fcc98-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fcc98-113">特性</span><span class="sxs-lookup"><span data-stu-id="fcc98-113">Attributes</span></span>  
  
|<span data-ttu-id="fcc98-114">特性</span><span class="sxs-lookup"><span data-stu-id="fcc98-114">Attribute</span></span>|<span data-ttu-id="fcc98-115">描述</span><span class="sxs-lookup"><span data-stu-id="fcc98-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fcc98-116">类型</span><span class="sxs-lookup"><span data-stu-id="fcc98-116">type</span></span>|<span data-ttu-id="fcc98-117">指定服务令牌解析程序的类型。</span><span class="sxs-lookup"><span data-stu-id="fcc98-117">Specifies the type of the service token resolver.</span></span> <span data-ttu-id="fcc98-118">任一<xref:System.IdentityModel.Selectors.SecurityTokenResolver>类型或派生自类型<xref:System.IdentityModel.Selectors.SecurityTokenResolver>类。</span><span class="sxs-lookup"><span data-stu-id="fcc98-118">Either the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> type or a type that derives from the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> class.</span></span> <span data-ttu-id="fcc98-119">有关如何指定详细信息`type`属性，请参阅 [自定义类型引用]。</span><span class="sxs-lookup"><span data-stu-id="fcc98-119">For more information about how to specify the `type` attribute, see [Custom Type References].</span></span> <span data-ttu-id="fcc98-120">必需。</span><span class="sxs-lookup"><span data-stu-id="fcc98-120">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fcc98-121">子元素</span><span class="sxs-lookup"><span data-stu-id="fcc98-121">Child Elements</span></span>  
 <span data-ttu-id="fcc98-122">无</span><span class="sxs-lookup"><span data-stu-id="fcc98-122">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fcc98-123">父元素</span><span class="sxs-lookup"><span data-stu-id="fcc98-123">Parent Elements</span></span>  
  
|<span data-ttu-id="fcc98-124">元素</span><span class="sxs-lookup"><span data-stu-id="fcc98-124">Element</span></span>|<span data-ttu-id="fcc98-125">描述</span><span class="sxs-lookup"><span data-stu-id="fcc98-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fcc98-126">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="fcc98-126">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="fcc98-127">提供配置集合的安全令牌处理程序。</span><span class="sxs-lookup"><span data-stu-id="fcc98-127">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fcc98-128">备注</span><span class="sxs-lookup"><span data-stu-id="fcc98-128">Remarks</span></span>  
 <span data-ttu-id="fcc98-129">服务的标记解析程序可以用于解析在传入令牌和消息上的加密令牌。</span><span class="sxs-lookup"><span data-stu-id="fcc98-129">The service token resolver can be used to resolve the encryption token on incoming tokens and messages.</span></span> <span data-ttu-id="fcc98-130">它用于检索应该用于解密传入令牌的密钥。</span><span class="sxs-lookup"><span data-stu-id="fcc98-130">It is used to retrieve the key that should be used to decrypt incoming tokens.</span></span> <span data-ttu-id="fcc98-131">必须指定`type`属性。</span><span class="sxs-lookup"><span data-stu-id="fcc98-131">You must specify the `type` attribute.</span></span> <span data-ttu-id="fcc98-132">指定的类型可以是<xref:System.IdentityModel.Selectors.SecurityTokenResolver>或派生自的自定义类型<xref:System.IdentityModel.Selectors.SecurityTokenResolver>类。</span><span class="sxs-lookup"><span data-stu-id="fcc98-132">The type specified can be either <xref:System.IdentityModel.Selectors.SecurityTokenResolver> or a custom type that derives from the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> class.</span></span>  
  
 <span data-ttu-id="fcc98-133">某些令牌处理程序，可以在配置中指定服务的标记解析程序设置。</span><span class="sxs-lookup"><span data-stu-id="fcc98-133">Some token handlers allow you to specify service token resolver settings in configuration.</span></span> <span data-ttu-id="fcc98-134">对于单个令牌处理程序的设置会覆盖上的安全令牌的处理程序集合的指定。</span><span class="sxs-lookup"><span data-stu-id="fcc98-134">Settings on individual token handlers override those specified on the security token handler collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fcc98-135">指定`<serviceTokenResolver>`元素的子元素作为[ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)元素已弃用，但仍支持向后兼容。</span><span class="sxs-lookup"><span data-stu-id="fcc98-135">Specifying the `<serviceTokenResolver>` element as a child element of the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="fcc98-136">上的设置`<securityTokenHandlerConfiguration>`元素上会覆盖`<identityConfiguration>`元素。</span><span class="sxs-lookup"><span data-stu-id="fcc98-136">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fcc98-137">示例</span><span class="sxs-lookup"><span data-stu-id="fcc98-137">Example</span></span>  
  
```xml  
<serviceTokenResolver type="MyNamespace.CustomTokenResolver, MyAssembly" />  
```
