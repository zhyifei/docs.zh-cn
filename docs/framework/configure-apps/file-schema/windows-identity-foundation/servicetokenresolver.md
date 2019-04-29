---
title: <serviceTokenResolver>
ms.date: 03/30/2017
ms.assetid: 6e9001e1-e064-4f47-84b2-46225c177746
author: BrucePerlerMS
ms.openlocfilehash: 1143717882652fc8a03947327b5f1ea89dde7373
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61793804"
---
# <a name="servicetokenresolver"></a><span data-ttu-id="54e9e-101">\<serviceTokenResolver></span><span class="sxs-lookup"><span data-stu-id="54e9e-101">\<serviceTokenResolver></span></span>
<span data-ttu-id="54e9e-102">注册的服务令牌解析程序使用的令牌处理程序集合中的处理程序。</span><span class="sxs-lookup"><span data-stu-id="54e9e-102">Registers the service token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="54e9e-103">服务标记解析器用于解析传入的令牌和消息中的加密令牌。</span><span class="sxs-lookup"><span data-stu-id="54e9e-103">The service token resolver is used to resolve the encryption token on incoming tokens and messages.</span></span>  
  
 <span data-ttu-id="54e9e-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="54e9e-104">\<system.identityModel></span></span>  
<span data-ttu-id="54e9e-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="54e9e-105">\<identityConfiguration></span></span>  
<span data-ttu-id="54e9e-106">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="54e9e-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="54e9e-107">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="54e9e-107">\<securityTokenHandlerConfiguration></span></span>  
<span data-ttu-id="54e9e-108">\<serviceTokenResolver></span><span class="sxs-lookup"><span data-stu-id="54e9e-108">\<serviceTokenResolver></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54e9e-109">语法</span><span class="sxs-lookup"><span data-stu-id="54e9e-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="54e9e-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="54e9e-110">Attributes and Elements</span></span>  
 <span data-ttu-id="54e9e-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="54e9e-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="54e9e-112">特性</span><span class="sxs-lookup"><span data-stu-id="54e9e-112">Attributes</span></span>  
  
|<span data-ttu-id="54e9e-113">特性</span><span class="sxs-lookup"><span data-stu-id="54e9e-113">Attribute</span></span>|<span data-ttu-id="54e9e-114">描述</span><span class="sxs-lookup"><span data-stu-id="54e9e-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="54e9e-115">类型</span><span class="sxs-lookup"><span data-stu-id="54e9e-115">type</span></span>|<span data-ttu-id="54e9e-116">指定的服务令牌解析程序的类型。</span><span class="sxs-lookup"><span data-stu-id="54e9e-116">Specifies the type of the service token resolver.</span></span> <span data-ttu-id="54e9e-117">任一<xref:System.IdentityModel.Selectors.SecurityTokenResolver>类型或派生类型<xref:System.IdentityModel.Selectors.SecurityTokenResolver>类。</span><span class="sxs-lookup"><span data-stu-id="54e9e-117">Either the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> type or a type that derives from the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> class.</span></span> <span data-ttu-id="54e9e-118">详细了解如何指定`type`属性，请参阅 [自定义类型引用]。</span><span class="sxs-lookup"><span data-stu-id="54e9e-118">For more information about how to specify the `type` attribute, see [Custom Type References].</span></span> <span data-ttu-id="54e9e-119">必需。</span><span class="sxs-lookup"><span data-stu-id="54e9e-119">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="54e9e-120">子元素</span><span class="sxs-lookup"><span data-stu-id="54e9e-120">Child Elements</span></span>  
 <span data-ttu-id="54e9e-121">None</span><span class="sxs-lookup"><span data-stu-id="54e9e-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="54e9e-122">父元素</span><span class="sxs-lookup"><span data-stu-id="54e9e-122">Parent Elements</span></span>  
  
|<span data-ttu-id="54e9e-123">元素</span><span class="sxs-lookup"><span data-stu-id="54e9e-123">Element</span></span>|<span data-ttu-id="54e9e-124">描述</span><span class="sxs-lookup"><span data-stu-id="54e9e-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="54e9e-125">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="54e9e-125">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="54e9e-126">提供配置集合的安全令牌处理程序。</span><span class="sxs-lookup"><span data-stu-id="54e9e-126">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="54e9e-127">备注</span><span class="sxs-lookup"><span data-stu-id="54e9e-127">Remarks</span></span>  
 <span data-ttu-id="54e9e-128">服务标记解析器可用于解析传入的令牌和消息中的加密令牌。</span><span class="sxs-lookup"><span data-stu-id="54e9e-128">The service token resolver can be used to resolve the encryption token on incoming tokens and messages.</span></span> <span data-ttu-id="54e9e-129">它用于检索应该用于解密传入令牌的密钥。</span><span class="sxs-lookup"><span data-stu-id="54e9e-129">It is used to retrieve the key that should be used to decrypt incoming tokens.</span></span> <span data-ttu-id="54e9e-130">必须指定`type`属性。</span><span class="sxs-lookup"><span data-stu-id="54e9e-130">You must specify the `type` attribute.</span></span> <span data-ttu-id="54e9e-131">指定的类型可以是<xref:System.IdentityModel.Selectors.SecurityTokenResolver>派生的自定义类型或<xref:System.IdentityModel.Selectors.SecurityTokenResolver>类。</span><span class="sxs-lookup"><span data-stu-id="54e9e-131">The type specified can be either <xref:System.IdentityModel.Selectors.SecurityTokenResolver> or a custom type that derives from the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> class.</span></span>  
  
 <span data-ttu-id="54e9e-132">一些令牌处理程序，可在配置中指定服务令牌解析器设置。</span><span class="sxs-lookup"><span data-stu-id="54e9e-132">Some token handlers allow you to specify service token resolver settings in configuration.</span></span> <span data-ttu-id="54e9e-133">单个标记处理程序上的设置将覆盖指定安全标记处理程序集合。</span><span class="sxs-lookup"><span data-stu-id="54e9e-133">Settings on individual token handlers override those specified on the security token handler collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="54e9e-134">指定`<serviceTokenResolver>`元素的子元素作为[ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)元素已被弃用，但仍然支持向后兼容。</span><span class="sxs-lookup"><span data-stu-id="54e9e-134">Specifying the `<serviceTokenResolver>` element as a child element of the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="54e9e-135">上的设置`<securityTokenHandlerConfiguration>`元素上会覆盖`<identityConfiguration>`元素。</span><span class="sxs-lookup"><span data-stu-id="54e9e-135">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="54e9e-136">示例</span><span class="sxs-lookup"><span data-stu-id="54e9e-136">Example</span></span>  
  
```xml  
<serviceTokenResolver type="MyNamespace.CustomTokenResolver, MyAssembly" />  
```
