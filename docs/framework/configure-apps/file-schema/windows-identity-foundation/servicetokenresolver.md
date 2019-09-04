---
title: <serviceTokenResolver>
ms.date: 03/30/2017
ms.assetid: 6e9001e1-e064-4f47-84b2-46225c177746
author: BrucePerlerMS
ms.openlocfilehash: 30a53c11b551623311f7ca3f957143fc702568a1
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251848"
---
# <a name="servicetokenresolver"></a><span data-ttu-id="03391-101">\<serviceTokenResolver></span><span class="sxs-lookup"><span data-stu-id="03391-101">\<serviceTokenResolver></span></span>
<span data-ttu-id="03391-102">注册令牌处理程序集合中的处理程序使用的服务令牌解析程序。</span><span class="sxs-lookup"><span data-stu-id="03391-102">Registers the service token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="03391-103">服务令牌解析器用于解析传入令牌和消息的加密令牌。</span><span class="sxs-lookup"><span data-stu-id="03391-103">The service token resolver is used to resolve the encryption token on incoming tokens and messages.</span></span>  
  
<span data-ttu-id="03391-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="03391-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="03391-105">&nbsp;&nbsp;[ **\<System.identitymodel >** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="03391-105">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="03391-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<identityConfiguration >** ](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="03391-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="03391-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<securityTokenHandlers >** ](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="03391-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="03391-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<securityTokenHandlerConfiguration >** ](securitytokenhandlerconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="03391-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlerConfiguration>**](securitytokenhandlerconfiguration.md)</span></span>\
<span data-ttu-id="03391-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<serviceTokenResolver >**</span><span class="sxs-lookup"><span data-stu-id="03391-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceTokenResolver>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03391-110">语法</span><span class="sxs-lookup"><span data-stu-id="03391-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="03391-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="03391-111">Attributes and Elements</span></span>  
 <span data-ttu-id="03391-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="03391-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="03391-113">特性</span><span class="sxs-lookup"><span data-stu-id="03391-113">Attributes</span></span>  
  
|<span data-ttu-id="03391-114">特性</span><span class="sxs-lookup"><span data-stu-id="03391-114">Attribute</span></span>|<span data-ttu-id="03391-115">描述</span><span class="sxs-lookup"><span data-stu-id="03391-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="03391-116">type</span><span class="sxs-lookup"><span data-stu-id="03391-116">type</span></span>|<span data-ttu-id="03391-117">指定服务令牌解析程序的类型。</span><span class="sxs-lookup"><span data-stu-id="03391-117">Specifies the type of the service token resolver.</span></span> <span data-ttu-id="03391-118">类型或派生<xref:System.IdentityModel.Selectors.SecurityTokenResolver>自类的类型。 <xref:System.IdentityModel.Selectors.SecurityTokenResolver></span><span class="sxs-lookup"><span data-stu-id="03391-118">Either the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> type or a type that derives from the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> class.</span></span> <span data-ttu-id="03391-119">有关如何指定`type`属性的详细信息，请参阅 [自定义类型引用]。</span><span class="sxs-lookup"><span data-stu-id="03391-119">For more information about how to specify the `type` attribute, see [Custom Type References].</span></span> <span data-ttu-id="03391-120">必需。</span><span class="sxs-lookup"><span data-stu-id="03391-120">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="03391-121">子元素</span><span class="sxs-lookup"><span data-stu-id="03391-121">Child Elements</span></span>  
 <span data-ttu-id="03391-122">无</span><span class="sxs-lookup"><span data-stu-id="03391-122">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="03391-123">父元素</span><span class="sxs-lookup"><span data-stu-id="03391-123">Parent Elements</span></span>  
  
|<span data-ttu-id="03391-124">元素</span><span class="sxs-lookup"><span data-stu-id="03391-124">Element</span></span>|<span data-ttu-id="03391-125">描述</span><span class="sxs-lookup"><span data-stu-id="03391-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="03391-126">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="03391-126">\<securityTokenHandlerConfiguration></span></span>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="03391-127">为安全标记处理程序的集合提供配置。</span><span class="sxs-lookup"><span data-stu-id="03391-127">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="03391-128">备注</span><span class="sxs-lookup"><span data-stu-id="03391-128">Remarks</span></span>  
 <span data-ttu-id="03391-129">服务令牌解析程序可用于解析传入令牌和消息的加密令牌。</span><span class="sxs-lookup"><span data-stu-id="03391-129">The service token resolver can be used to resolve the encryption token on incoming tokens and messages.</span></span> <span data-ttu-id="03391-130">它用于检索应该用于解密传入令牌的密钥。</span><span class="sxs-lookup"><span data-stu-id="03391-130">It is used to retrieve the key that should be used to decrypt incoming tokens.</span></span> <span data-ttu-id="03391-131">您必须指定`type`属性。</span><span class="sxs-lookup"><span data-stu-id="03391-131">You must specify the `type` attribute.</span></span> <span data-ttu-id="03391-132">指定的类型可以是<xref:System.IdentityModel.Selectors.SecurityTokenResolver>或<xref:System.IdentityModel.Selectors.SecurityTokenResolver>从类派生的自定义类型。</span><span class="sxs-lookup"><span data-stu-id="03391-132">The type specified can be either <xref:System.IdentityModel.Selectors.SecurityTokenResolver> or a custom type that derives from the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> class.</span></span>  
  
 <span data-ttu-id="03391-133">某些标记处理程序允许您在配置中指定服务令牌解析器设置。</span><span class="sxs-lookup"><span data-stu-id="03391-133">Some token handlers allow you to specify service token resolver settings in configuration.</span></span> <span data-ttu-id="03391-134">各个标记处理程序上的设置将替代在安全令牌处理程序集合中指定的设置。</span><span class="sxs-lookup"><span data-stu-id="03391-134">Settings on individual token handlers override those specified on the security token handler collection.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="03391-135">将元素指定为[ \<identityConfiguration >](identityconfiguration.md)元素的子元素已被弃用，但仍支持向后兼容。 `<serviceTokenResolver>`</span><span class="sxs-lookup"><span data-stu-id="03391-135">Specifying the `<serviceTokenResolver>` element as a child element of the [\<identityConfiguration>](identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="03391-136">元素上的`<securityTokenHandlerConfiguration>`设置将替代`<identityConfiguration>`元素上的设置。</span><span class="sxs-lookup"><span data-stu-id="03391-136">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="03391-137">示例</span><span class="sxs-lookup"><span data-stu-id="03391-137">Example</span></span>  
  
```xml  
<serviceTokenResolver type="MyNamespace.CustomTokenResolver, MyAssembly" />  
```
 