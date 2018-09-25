---
title: '&lt;serviceTokenResolver&gt;'
ms.date: 03/30/2017
ms.assetid: 6e9001e1-e064-4f47-84b2-46225c177746
author: BrucePerlerMS
ms.openlocfilehash: d4b64e2c88e153834b7cf5a83bd6258b6dfd471f
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/25/2018
ms.locfileid: "47075291"
---
# <a name="ltservicetokenresolvergt"></a><span data-ttu-id="7f886-102">&lt;serviceTokenResolver&gt;</span><span class="sxs-lookup"><span data-stu-id="7f886-102">&lt;serviceTokenResolver&gt;</span></span>
<span data-ttu-id="7f886-103">注册的服务令牌解析程序使用的令牌处理程序集合中的处理程序。</span><span class="sxs-lookup"><span data-stu-id="7f886-103">Registers the service token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="7f886-104">服务标记解析器用于解析传入的令牌和消息中的加密令牌。</span><span class="sxs-lookup"><span data-stu-id="7f886-104">The service token resolver is used to resolve the encryption token on incoming tokens and messages.</span></span>  
  
 <span data-ttu-id="7f886-105">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="7f886-105">\<system.identityModel></span></span>  
<span data-ttu-id="7f886-106">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="7f886-106">\<identityConfiguration></span></span>  
<span data-ttu-id="7f886-107">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="7f886-107">\<securityTokenHandlers></span></span>  
<span data-ttu-id="7f886-108">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="7f886-108">\<securityTokenHandlerConfiguration></span></span>  
<span data-ttu-id="7f886-109">\<serviceTokenResolver ></span><span class="sxs-lookup"><span data-stu-id="7f886-109">\<serviceTokenResolver></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7f886-110">语法</span><span class="sxs-lookup"><span data-stu-id="7f886-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7f886-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="7f886-111">Attributes and Elements</span></span>  
 <span data-ttu-id="7f886-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="7f886-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7f886-113">特性</span><span class="sxs-lookup"><span data-stu-id="7f886-113">Attributes</span></span>  
  
|<span data-ttu-id="7f886-114">特性</span><span class="sxs-lookup"><span data-stu-id="7f886-114">Attribute</span></span>|<span data-ttu-id="7f886-115">描述</span><span class="sxs-lookup"><span data-stu-id="7f886-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7f886-116">类型</span><span class="sxs-lookup"><span data-stu-id="7f886-116">type</span></span>|<span data-ttu-id="7f886-117">指定的服务令牌解析程序的类型。</span><span class="sxs-lookup"><span data-stu-id="7f886-117">Specifies the type of the service token resolver.</span></span> <span data-ttu-id="7f886-118">任一<xref:System.IdentityModel.Selectors.SecurityTokenResolver>类型或派生类型<xref:System.IdentityModel.Selectors.SecurityTokenResolver>类。</span><span class="sxs-lookup"><span data-stu-id="7f886-118">Either the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> type or a type that derives from the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> class.</span></span> <span data-ttu-id="7f886-119">详细了解如何指定`type`属性，请参阅 [自定义类型引用]。</span><span class="sxs-lookup"><span data-stu-id="7f886-119">For more information about how to specify the `type` attribute, see [Custom Type References].</span></span> <span data-ttu-id="7f886-120">必须的。</span><span class="sxs-lookup"><span data-stu-id="7f886-120">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7f886-121">子元素</span><span class="sxs-lookup"><span data-stu-id="7f886-121">Child Elements</span></span>  
 <span data-ttu-id="7f886-122">无</span><span class="sxs-lookup"><span data-stu-id="7f886-122">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7f886-123">父元素</span><span class="sxs-lookup"><span data-stu-id="7f886-123">Parent Elements</span></span>  
  
|<span data-ttu-id="7f886-124">元素</span><span class="sxs-lookup"><span data-stu-id="7f886-124">Element</span></span>|<span data-ttu-id="7f886-125">描述</span><span class="sxs-lookup"><span data-stu-id="7f886-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7f886-126">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="7f886-126">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="7f886-127">提供配置集合的安全令牌处理程序。</span><span class="sxs-lookup"><span data-stu-id="7f886-127">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7f886-128">备注</span><span class="sxs-lookup"><span data-stu-id="7f886-128">Remarks</span></span>  
 <span data-ttu-id="7f886-129">服务标记解析器可用于解析传入的令牌和消息中的加密令牌。</span><span class="sxs-lookup"><span data-stu-id="7f886-129">The service token resolver can be used to resolve the encryption token on incoming tokens and messages.</span></span> <span data-ttu-id="7f886-130">它用于检索应该用于解密传入令牌的密钥。</span><span class="sxs-lookup"><span data-stu-id="7f886-130">It is used to retrieve the key that should be used to decrypt incoming tokens.</span></span> <span data-ttu-id="7f886-131">必须指定`type`属性。</span><span class="sxs-lookup"><span data-stu-id="7f886-131">You must specify the `type` attribute.</span></span> <span data-ttu-id="7f886-132">指定的类型可以是<xref:System.IdentityModel.Selectors.SecurityTokenResolver>派生的自定义类型或<xref:System.IdentityModel.Selectors.SecurityTokenResolver>类。</span><span class="sxs-lookup"><span data-stu-id="7f886-132">The type specified can be either <xref:System.IdentityModel.Selectors.SecurityTokenResolver> or a custom type that derives from the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> class.</span></span>  
  
 <span data-ttu-id="7f886-133">一些令牌处理程序，可在配置中指定服务令牌解析器设置。</span><span class="sxs-lookup"><span data-stu-id="7f886-133">Some token handlers allow you to specify service token resolver settings in configuration.</span></span> <span data-ttu-id="7f886-134">单个标记处理程序上的设置将覆盖指定安全标记处理程序集合。</span><span class="sxs-lookup"><span data-stu-id="7f886-134">Settings on individual token handlers override those specified on the security token handler collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7f886-135">指定`<serviceTokenResolver>`元素的子元素作为[ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)元素已被弃用，但仍然支持向后兼容。</span><span class="sxs-lookup"><span data-stu-id="7f886-135">Specifying the `<serviceTokenResolver>` element as a child element of the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="7f886-136">上的设置`<securityTokenHandlerConfiguration>`元素上会覆盖`<identityConfiguration>`元素。</span><span class="sxs-lookup"><span data-stu-id="7f886-136">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7f886-137">示例</span><span class="sxs-lookup"><span data-stu-id="7f886-137">Example</span></span>  
  
```xml  
<serviceTokenResolver type="MyNamespace.CustomTokenResolver, MyAssembly" />  
```
