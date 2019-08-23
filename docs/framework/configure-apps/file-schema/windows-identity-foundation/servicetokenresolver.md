---
title: <serviceTokenResolver>
ms.date: 03/30/2017
ms.assetid: 6e9001e1-e064-4f47-84b2-46225c177746
author: BrucePerlerMS
ms.openlocfilehash: 69d34cb54c2236f178ac4291ed24a3f5b45db48e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69923112"
---
# <a name="servicetokenresolver"></a><span data-ttu-id="98cf6-101">\<serviceTokenResolver></span><span class="sxs-lookup"><span data-stu-id="98cf6-101">\<serviceTokenResolver></span></span>
<span data-ttu-id="98cf6-102">注册令牌处理程序集合中的处理程序使用的服务令牌解析程序。</span><span class="sxs-lookup"><span data-stu-id="98cf6-102">Registers the service token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="98cf6-103">服务令牌解析器用于解析传入令牌和消息的加密令牌。</span><span class="sxs-lookup"><span data-stu-id="98cf6-103">The service token resolver is used to resolve the encryption token on incoming tokens and messages.</span></span>  
  
 <span data-ttu-id="98cf6-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="98cf6-104">\<system.identityModel></span></span>  
<span data-ttu-id="98cf6-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="98cf6-105">\<identityConfiguration></span></span>  
<span data-ttu-id="98cf6-106">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="98cf6-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="98cf6-107">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="98cf6-107">\<securityTokenHandlerConfiguration></span></span>  
<span data-ttu-id="98cf6-108">\<serviceTokenResolver></span><span class="sxs-lookup"><span data-stu-id="98cf6-108">\<serviceTokenResolver></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98cf6-109">语法</span><span class="sxs-lookup"><span data-stu-id="98cf6-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="98cf6-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="98cf6-110">Attributes and Elements</span></span>  
 <span data-ttu-id="98cf6-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="98cf6-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="98cf6-112">特性</span><span class="sxs-lookup"><span data-stu-id="98cf6-112">Attributes</span></span>  
  
|<span data-ttu-id="98cf6-113">特性</span><span class="sxs-lookup"><span data-stu-id="98cf6-113">Attribute</span></span>|<span data-ttu-id="98cf6-114">描述</span><span class="sxs-lookup"><span data-stu-id="98cf6-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="98cf6-115">type</span><span class="sxs-lookup"><span data-stu-id="98cf6-115">type</span></span>|<span data-ttu-id="98cf6-116">指定服务令牌解析程序的类型。</span><span class="sxs-lookup"><span data-stu-id="98cf6-116">Specifies the type of the service token resolver.</span></span> <span data-ttu-id="98cf6-117">类型或派生<xref:System.IdentityModel.Selectors.SecurityTokenResolver>自类的类型。 <xref:System.IdentityModel.Selectors.SecurityTokenResolver></span><span class="sxs-lookup"><span data-stu-id="98cf6-117">Either the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> type or a type that derives from the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> class.</span></span> <span data-ttu-id="98cf6-118">有关如何指定`type`属性的详细信息, 请参阅 [自定义类型引用]。</span><span class="sxs-lookup"><span data-stu-id="98cf6-118">For more information about how to specify the `type` attribute, see [Custom Type References].</span></span> <span data-ttu-id="98cf6-119">必需。</span><span class="sxs-lookup"><span data-stu-id="98cf6-119">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="98cf6-120">子元素</span><span class="sxs-lookup"><span data-stu-id="98cf6-120">Child Elements</span></span>  
 <span data-ttu-id="98cf6-121">无</span><span class="sxs-lookup"><span data-stu-id="98cf6-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="98cf6-122">父元素</span><span class="sxs-lookup"><span data-stu-id="98cf6-122">Parent Elements</span></span>  
  
|<span data-ttu-id="98cf6-123">元素</span><span class="sxs-lookup"><span data-stu-id="98cf6-123">Element</span></span>|<span data-ttu-id="98cf6-124">描述</span><span class="sxs-lookup"><span data-stu-id="98cf6-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="98cf6-125">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="98cf6-125">\<securityTokenHandlerConfiguration></span></span>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="98cf6-126">为安全标记处理程序的集合提供配置。</span><span class="sxs-lookup"><span data-stu-id="98cf6-126">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="98cf6-127">备注</span><span class="sxs-lookup"><span data-stu-id="98cf6-127">Remarks</span></span>  
 <span data-ttu-id="98cf6-128">服务令牌解析程序可用于解析传入令牌和消息的加密令牌。</span><span class="sxs-lookup"><span data-stu-id="98cf6-128">The service token resolver can be used to resolve the encryption token on incoming tokens and messages.</span></span> <span data-ttu-id="98cf6-129">它用于检索应该用于解密传入令牌的密钥。</span><span class="sxs-lookup"><span data-stu-id="98cf6-129">It is used to retrieve the key that should be used to decrypt incoming tokens.</span></span> <span data-ttu-id="98cf6-130">您必须指定`type`属性。</span><span class="sxs-lookup"><span data-stu-id="98cf6-130">You must specify the `type` attribute.</span></span> <span data-ttu-id="98cf6-131">指定的类型可以是<xref:System.IdentityModel.Selectors.SecurityTokenResolver>或<xref:System.IdentityModel.Selectors.SecurityTokenResolver>从类派生的自定义类型。</span><span class="sxs-lookup"><span data-stu-id="98cf6-131">The type specified can be either <xref:System.IdentityModel.Selectors.SecurityTokenResolver> or a custom type that derives from the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> class.</span></span>  
  
 <span data-ttu-id="98cf6-132">某些标记处理程序允许您在配置中指定服务令牌解析器设置。</span><span class="sxs-lookup"><span data-stu-id="98cf6-132">Some token handlers allow you to specify service token resolver settings in configuration.</span></span> <span data-ttu-id="98cf6-133">各个标记处理程序上的设置将替代在安全令牌处理程序集合中指定的设置。</span><span class="sxs-lookup"><span data-stu-id="98cf6-133">Settings on individual token handlers override those specified on the security token handler collection.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="98cf6-134">将元素指定为[ \<identityConfiguration >](identityconfiguration.md)元素的子元素已被弃用, 但仍支持向后兼容。 `<serviceTokenResolver>`</span><span class="sxs-lookup"><span data-stu-id="98cf6-134">Specifying the `<serviceTokenResolver>` element as a child element of the [\<identityConfiguration>](identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="98cf6-135">元素上的`<securityTokenHandlerConfiguration>`设置将替代`<identityConfiguration>`元素上的设置。</span><span class="sxs-lookup"><span data-stu-id="98cf6-135">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="98cf6-136">示例</span><span class="sxs-lookup"><span data-stu-id="98cf6-136">Example</span></span>  
  
```xml  
<serviceTokenResolver type="MyNamespace.CustomTokenResolver, MyAssembly" />  
```
