---
title: <serviceAuthorization> 元素
ms.date: 03/30/2017
ms.assetid: 18cddad5-ddcb-4839-a0ac-1d6f6ab783ca
ms.openlocfilehash: b73e2049afb460bf9be8b76ee272ba0547b61453
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69936406"
---
# <a name="serviceauthorization-element"></a><span data-ttu-id="9f898-102">\<serviceAuthorization > 元素</span><span class="sxs-lookup"><span data-stu-id="9f898-102">\<serviceAuthorization> element</span></span>
<span data-ttu-id="9f898-103">指定用于授予服务操作访问权限的设置。</span><span class="sxs-lookup"><span data-stu-id="9f898-103">Specifies settings that authorize access to service operations</span></span>  
  
 <span data-ttu-id="9f898-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="9f898-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="9f898-105">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="9f898-105">\<behaviors></span></span>  
<span data-ttu-id="9f898-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="9f898-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="9f898-107">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="9f898-107">\<behavior></span></span>  
<span data-ttu-id="9f898-108">\<serviceAuthorization></span><span class="sxs-lookup"><span data-stu-id="9f898-108">\<serviceAuthorization></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f898-109">语法</span><span class="sxs-lookup"><span data-stu-id="9f898-109">Syntax</span></span>  
  
```xml  
<serviceAuthorization impersonateCallerForAllOperations="Boolean"
                      principalPermissionMode="None/UseWindowsGroups/UseAspNetRoles/Custom"
                      roleProviderName="String"
                      serviceAuthorizationManagerType="String">
  <authorizationPolicies>
    <add policyType="String" />
  </authorizationPolicies>
</serviceAuthorization>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9f898-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="9f898-110">Attributes and Elements</span></span>  
 <span data-ttu-id="9f898-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="9f898-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9f898-112">特性</span><span class="sxs-lookup"><span data-stu-id="9f898-112">Attributes</span></span>  
  
|<span data-ttu-id="9f898-113">特性</span><span class="sxs-lookup"><span data-stu-id="9f898-113">Attribute</span></span>|<span data-ttu-id="9f898-114">描述</span><span class="sxs-lookup"><span data-stu-id="9f898-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9f898-115">impersonateCallerForAllOperations</span><span class="sxs-lookup"><span data-stu-id="9f898-115">impersonateCallerForAllOperations</span></span>|<span data-ttu-id="9f898-116">一个布尔值，指定是否服务中的所有操作都模拟调用方。</span><span class="sxs-lookup"><span data-stu-id="9f898-116">A Boolean value that specifies if all the operations in the service impersonate the caller.</span></span> <span data-ttu-id="9f898-117">默认值为 `false`。</span><span class="sxs-lookup"><span data-stu-id="9f898-117">The default is `false`.</span></span><br /><br /> <span data-ttu-id="9f898-118">当特定服务操作模拟调用方时，线程上下文会在执行指定服务前切换为调用方上下文。</span><span class="sxs-lookup"><span data-stu-id="9f898-118">When a specific service operation impersonates the caller, the thread context is switched to the caller context before executing the specified service.</span></span>|  
|<span data-ttu-id="9f898-119">principalPermissionMode</span><span class="sxs-lookup"><span data-stu-id="9f898-119">principalPermissionMode</span></span>|<span data-ttu-id="9f898-120">设置用于在服务器上执行操作的主体。</span><span class="sxs-lookup"><span data-stu-id="9f898-120">Sets the principal used to carry out operations on the server.</span></span> <span data-ttu-id="9f898-121">包括以下值：</span><span class="sxs-lookup"><span data-stu-id="9f898-121">Values include the following:</span></span><br /><br /> <span data-ttu-id="9f898-122">-无</span><span class="sxs-lookup"><span data-stu-id="9f898-122">-   None</span></span><br /><span data-ttu-id="9f898-123">-UseWindowsGroups</span><span class="sxs-lookup"><span data-stu-id="9f898-123">-   UseWindowsGroups</span></span><br /><span data-ttu-id="9f898-124">-   UseAspNetRoles</span><span class="sxs-lookup"><span data-stu-id="9f898-124">-   UseAspNetRoles</span></span><br /><span data-ttu-id="9f898-125">-Custom</span><span class="sxs-lookup"><span data-stu-id="9f898-125">-   Custom</span></span><br /><br /> <span data-ttu-id="9f898-126">默认值为 UseWindowsGroups。</span><span class="sxs-lookup"><span data-stu-id="9f898-126">The default value is UseWindowsGroups.</span></span> <span data-ttu-id="9f898-127">此值的类型为 <xref:System.ServiceModel.Description.PrincipalPermissionMode>。</span><span class="sxs-lookup"><span data-stu-id="9f898-127">The value is of type <xref:System.ServiceModel.Description.PrincipalPermissionMode>.</span></span> <span data-ttu-id="9f898-128">有关使用此属性的详细信息, 请[参阅如何:使用 PrincipalPermissionAttribute 类](../../../wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md)限制访问。</span><span class="sxs-lookup"><span data-stu-id="9f898-128">For more information on using this attribute, see [How to: Restrict Access with the PrincipalPermissionAttribute Class](../../../wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md).</span></span>|  
|<span data-ttu-id="9f898-129">roleProviderName</span><span class="sxs-lookup"><span data-stu-id="9f898-129">roleProviderName</span></span>|<span data-ttu-id="9f898-130">一个字符串，指定为 Windows Communication Foundation (WCF) 应用程序提供角色信息的角色提供程序的名称。</span><span class="sxs-lookup"><span data-stu-id="9f898-130">A string that specifies the name of the role provider, which provides role information for a Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="9f898-131">默认值为一个空字符串。</span><span class="sxs-lookup"><span data-stu-id="9f898-131">The default is an empty string.</span></span>|  
|<span data-ttu-id="9f898-132">ServiceAuthorizationManagerType</span><span class="sxs-lookup"><span data-stu-id="9f898-132">ServiceAuthorizationManagerType</span></span>|<span data-ttu-id="9f898-133">一个包含服务授权管理器的类型的字符串。</span><span class="sxs-lookup"><span data-stu-id="9f898-133">A string containing the type of the service authorization manager.</span></span> <span data-ttu-id="9f898-134">有关详细信息，请参阅 <xref:System.ServiceModel.ServiceAuthorizationManager> 。</span><span class="sxs-lookup"><span data-stu-id="9f898-134">For more information, see <xref:System.ServiceModel.ServiceAuthorizationManager>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9f898-135">子元素</span><span class="sxs-lookup"><span data-stu-id="9f898-135">Child Elements</span></span>  
  
|<span data-ttu-id="9f898-136">元素</span><span class="sxs-lookup"><span data-stu-id="9f898-136">Element</span></span>|<span data-ttu-id="9f898-137">描述</span><span class="sxs-lookup"><span data-stu-id="9f898-137">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9f898-138">authorizationPolicies</span><span class="sxs-lookup"><span data-stu-id="9f898-138">authorizationPolicies</span></span>|<span data-ttu-id="9f898-139">包含可使用 `add` 关键字添加的授权策略类型的集合。</span><span class="sxs-lookup"><span data-stu-id="9f898-139">Contains a collection of authorization policy types, which can be added using the `add` keyword.</span></span> <span data-ttu-id="9f898-140">每个授权类型都包含一个所需的 `policyType` 属性，此属性是一个字符串。</span><span class="sxs-lookup"><span data-stu-id="9f898-140">Each authorization policy contains a single required `policyType` attribute that is a string.</span></span> <span data-ttu-id="9f898-141">该属性指定一个授权策略，可以将一组输入声明转换为另一组声明。</span><span class="sxs-lookup"><span data-stu-id="9f898-141">The attribute specifies an authorization policy, which enables transformation of one set of input claims into another set of claims.</span></span> <span data-ttu-id="9f898-142">可以根据该授权策略来授予或拒绝访问控制。</span><span class="sxs-lookup"><span data-stu-id="9f898-142">Access control can be granted or denied based on that.</span></span> <span data-ttu-id="9f898-143">有关详细信息，请参阅 <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElement>。</span><span class="sxs-lookup"><span data-stu-id="9f898-143">For more information, see <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9f898-144">父元素</span><span class="sxs-lookup"><span data-stu-id="9f898-144">Parent Elements</span></span>  
  
|<span data-ttu-id="9f898-145">元素</span><span class="sxs-lookup"><span data-stu-id="9f898-145">Element</span></span>|<span data-ttu-id="9f898-146">描述</span><span class="sxs-lookup"><span data-stu-id="9f898-146">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9f898-147">\<behavior></span><span class="sxs-lookup"><span data-stu-id="9f898-147">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="9f898-148">包含服务行为的设置集合。</span><span class="sxs-lookup"><span data-stu-id="9f898-148">Contains a collection of settings for the behavior of a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9f898-149">备注</span><span class="sxs-lookup"><span data-stu-id="9f898-149">Remarks</span></span>  
 <span data-ttu-id="9f898-150">本节包含一些影响授权、自定义角色提供程序和模拟的元素。</span><span class="sxs-lookup"><span data-stu-id="9f898-150">This section contains elements affecting authorization, custom role providers, and impersonation.</span></span>  
  
 <span data-ttu-id="9f898-151">`principalPermissionMode` 属性指定在授权使用受保护方法时要使用的用户组。</span><span class="sxs-lookup"><span data-stu-id="9f898-151">The `principalPermissionMode` attribute specifies the groups of users to use when authorizing use of a protected method.</span></span> <span data-ttu-id="9f898-152">默认值为 `UseWindowsGroups`，该值指定在 Windows 组（例如，“Administrators”或“Users”）中搜索试图访问某个资源的标识。</span><span class="sxs-lookup"><span data-stu-id="9f898-152">The default value is `UseWindowsGroups` and specifies that Windows groups, such as "Administrators" or "Users," are searched for an identity trying to access a resource.</span></span> <span data-ttu-id="9f898-153">你还可以指定`UseAspNetRoles`以使用\<在 system.web > 元素下配置的自定义角色提供程序, 如下面的代码所示。</span><span class="sxs-lookup"><span data-stu-id="9f898-153">You can also specify `UseAspNetRoles` to use a custom role provider that is configured under the \<system.web> element, as shown in the following code.</span></span>  
  
```xml  
<system.web>
  <membership defaultProvider="SqlProvider"
              userIsOnlineTimeWindow="15">
    <providers>
      <clear />
      <add name="SqlProvider"
           type="System.Web.Security.SqlMembershipProvider"
           connectionStringName="SqlConn"
           applicationName="MembershipProvider"
           enablePasswordRetrieval="false"
           enablePasswordReset="false"
           requiresQuestionAndAnswer="false"
           requiresUniqueEmail="true"
           passwordFormat="Hashed" />
    </providers>
  </membership>
  <!-- Other configuration code not shown. -->
</system.web>
```  
  
 <span data-ttu-id="9f898-154">下面的代码演示与 `roleProviderName` 特性一起使用的 `principalPermissionMode`。</span><span class="sxs-lookup"><span data-stu-id="9f898-154">The following code shows the `roleProviderName` used with the `principalPermissionMode` attribute.</span></span>  
  
```xml  
<behaviors>
  <behavior name="ServiceBehaviour">
    <serviceAuthorization principalPermissionMode ="UseAspNetRoles"
                          roleProviderName ="SqlProvider" />
  </behavior>
  <!-- Other configuration code not shown. -->
</behaviors>
```  
  
 <span data-ttu-id="9f898-155">有关使用此配置元素的详细示例, 请参阅[授权访问服务操作](../../../wcf/samples/authorizing-access-to-service-operations.md)和[授权策略](../../../wcf/samples/authorization-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="9f898-155">For a detailed example of using this configuration element, see [Authorizing Access to Service Operations](../../../wcf/samples/authorizing-access-to-service-operations.md) and [Authorization Policy](../../../wcf/samples/authorization-policy.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f898-156">请参阅</span><span class="sxs-lookup"><span data-stu-id="9f898-156">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement>
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>
- [<span data-ttu-id="9f898-157">安全行为</span><span class="sxs-lookup"><span data-stu-id="9f898-157">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="9f898-158">授予对服务操作的权限</span><span class="sxs-lookup"><span data-stu-id="9f898-158">Authorizing Access to Service Operations</span></span>](../../../wcf/samples/authorizing-access-to-service-operations.md)
- [<span data-ttu-id="9f898-159">如何：为服务创建自定义授权管理器</span><span class="sxs-lookup"><span data-stu-id="9f898-159">How to: Create a Custom Authorization Manager for a Service</span></span>](../../../wcf/extending/how-to-create-a-custom-authorization-manager-for-a-service.md)
- [<span data-ttu-id="9f898-160">如何：使用 PrincipalPermissionAttribute 类限制访问</span><span class="sxs-lookup"><span data-stu-id="9f898-160">How to: Restrict Access with the PrincipalPermissionAttribute Class</span></span>](../../../wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md)
- [<span data-ttu-id="9f898-161">授权策略</span><span class="sxs-lookup"><span data-stu-id="9f898-161">Authorization Policy</span></span>](../../../wcf/samples/authorization-policy.md)
