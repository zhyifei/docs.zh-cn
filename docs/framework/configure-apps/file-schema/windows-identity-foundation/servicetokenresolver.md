---
title: <serviceTokenResolver>
ms.date: 03/30/2017
ms.assetid: 6e9001e1-e064-4f47-84b2-46225c177746
author: BrucePerlerMS
ms.openlocfilehash: 0983380e553acfe246d6b987784d818b8ae85b17
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152575"
---
# <a name="servicetokenresolver"></a><span data-ttu-id="25693-101">\<服务令牌解析器></span><span class="sxs-lookup"><span data-stu-id="25693-101">\<serviceTokenResolver></span></span>
<span data-ttu-id="25693-102">注册令牌处理程序集合中处理程序使用的服务令牌解析器。</span><span class="sxs-lookup"><span data-stu-id="25693-102">Registers the service token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="25693-103">服务令牌解析器用于解析传入令牌和消息上的加密令牌。</span><span class="sxs-lookup"><span data-stu-id="25693-103">The service token resolver is used to resolve the encryption token on incoming tokens and messages.</span></span>  
  
<span data-ttu-id="25693-104">[**\<配置>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="25693-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="25693-105">&nbsp;&nbsp;[**\<系统.身份模型>**](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="25693-105">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="25693-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<身份配置>**](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="25693-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="25693-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<安全令牌处理程序>**](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="25693-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="25693-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<安全令牌处理程序配置>**](securitytokenhandlerconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="25693-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlerConfiguration>**](securitytokenhandlerconfiguration.md)</span></span>\
<span data-ttu-id="25693-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<服务令牌解析器>**</span><span class="sxs-lookup"><span data-stu-id="25693-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceTokenResolver>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25693-110">语法</span><span class="sxs-lookup"><span data-stu-id="25693-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="25693-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="25693-111">Attributes and Elements</span></span>  
 <span data-ttu-id="25693-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="25693-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="25693-113">属性</span><span class="sxs-lookup"><span data-stu-id="25693-113">Attributes</span></span>  
  
|<span data-ttu-id="25693-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="25693-114">Attribute</span></span>|<span data-ttu-id="25693-115">说明</span><span class="sxs-lookup"><span data-stu-id="25693-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="25693-116">type</span><span class="sxs-lookup"><span data-stu-id="25693-116">type</span></span>|<span data-ttu-id="25693-117">指定服务令牌解析器的类型。</span><span class="sxs-lookup"><span data-stu-id="25693-117">Specifies the type of the service token resolver.</span></span> <span data-ttu-id="25693-118">派生自<xref:System.IdentityModel.Selectors.SecurityTokenResolver><xref:System.IdentityModel.Selectors.SecurityTokenResolver>类的类型或类型。</span><span class="sxs-lookup"><span data-stu-id="25693-118">Either the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> type or a type that derives from the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> class.</span></span> <span data-ttu-id="25693-119">有关如何指定属性的详细信息，`type`请参阅 [自定义类型引用]。</span><span class="sxs-lookup"><span data-stu-id="25693-119">For more information about how to specify the `type` attribute, see [Custom Type References].</span></span> <span data-ttu-id="25693-120">必需。</span><span class="sxs-lookup"><span data-stu-id="25693-120">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="25693-121">子元素</span><span class="sxs-lookup"><span data-stu-id="25693-121">Child Elements</span></span>  
 <span data-ttu-id="25693-122">无</span><span class="sxs-lookup"><span data-stu-id="25693-122">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="25693-123">父元素</span><span class="sxs-lookup"><span data-stu-id="25693-123">Parent Elements</span></span>  
  
|<span data-ttu-id="25693-124">元素</span><span class="sxs-lookup"><span data-stu-id="25693-124">Element</span></span>|<span data-ttu-id="25693-125">说明</span><span class="sxs-lookup"><span data-stu-id="25693-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="25693-126">\<安全令牌处理程序配置></span><span class="sxs-lookup"><span data-stu-id="25693-126">\<securityTokenHandlerConfiguration></span></span>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="25693-127">为安全令牌处理程序的集合提供配置。</span><span class="sxs-lookup"><span data-stu-id="25693-127">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="25693-128">备注</span><span class="sxs-lookup"><span data-stu-id="25693-128">Remarks</span></span>  
 <span data-ttu-id="25693-129">服务令牌解析器可用于解析传入令牌和消息上的加密令牌。</span><span class="sxs-lookup"><span data-stu-id="25693-129">The service token resolver can be used to resolve the encryption token on incoming tokens and messages.</span></span> <span data-ttu-id="25693-130">它用于检索应用于解密传入令牌的密钥。</span><span class="sxs-lookup"><span data-stu-id="25693-130">It is used to retrieve the key that should be used to decrypt incoming tokens.</span></span> <span data-ttu-id="25693-131">必须指定该`type`属性。</span><span class="sxs-lookup"><span data-stu-id="25693-131">You must specify the `type` attribute.</span></span> <span data-ttu-id="25693-132">指定的类型可以是 或<xref:System.IdentityModel.Selectors.SecurityTokenResolver>派生自类的<xref:System.IdentityModel.Selectors.SecurityTokenResolver>自定义类型。</span><span class="sxs-lookup"><span data-stu-id="25693-132">The type specified can be either <xref:System.IdentityModel.Selectors.SecurityTokenResolver> or a custom type that derives from the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> class.</span></span>  
  
 <span data-ttu-id="25693-133">某些令牌处理程序允许您在配置中指定服务令牌解析器设置。</span><span class="sxs-lookup"><span data-stu-id="25693-133">Some token handlers allow you to specify service token resolver settings in configuration.</span></span> <span data-ttu-id="25693-134">各个令牌处理程序上的设置将覆盖在安全令牌处理程序集合上指定的设置。</span><span class="sxs-lookup"><span data-stu-id="25693-134">Settings on individual token handlers override those specified on the security token handler collection.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="25693-135">将`<serviceTokenResolver>`元素指定为[\<标识配置>](identityconfiguration.md)元素的子元素已被弃用，但仍支持向后兼容性。</span><span class="sxs-lookup"><span data-stu-id="25693-135">Specifying the `<serviceTokenResolver>` element as a child element of the [\<identityConfiguration>](identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="25693-136">元素上的`<securityTokenHandlerConfiguration>`设置将覆盖元素上的`<identityConfiguration>`设置。</span><span class="sxs-lookup"><span data-stu-id="25693-136">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="25693-137">示例</span><span class="sxs-lookup"><span data-stu-id="25693-137">Example</span></span>  
  
```xml  
<serviceTokenResolver type="MyNamespace.CustomTokenResolver, MyAssembly" />  
```
