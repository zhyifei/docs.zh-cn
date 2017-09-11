---
title: "缓解：MemberDescriptor.Equals"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cf3735f0-0dd4-4bef-b4b0-575264e10f39
caps.latest.revision: 7
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 4989d3c2611b500063158955f102931902e1ab32
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="mitigation-memberdescriptorequals"></a><span data-ttu-id="3187a-102">缓解：MemberDescriptor.Equals</span><span class="sxs-lookup"><span data-stu-id="3187a-102">Mitigation: MemberDescriptor.Equals</span></span>
<span data-ttu-id="3187a-103">自面向 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] 的应用起，<xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=fullName> 方法的实现已更改。</span><span class="sxs-lookup"><span data-stu-id="3187a-103">Starting with apps that target the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], the implementation of the <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=fullName> method has changed.</span></span> <span data-ttu-id="3187a-104">由于 `System.ComponentModel.EventDescriptor.Equals` 和 `System.ComponentModel.PropertyDescriptor.Equals` 方法继承基类实现代码，因此这一更改还会影响这些方法。</span><span class="sxs-lookup"><span data-stu-id="3187a-104">Because the `System.ComponentModel.EventDescriptor.Equals` and  `System.ComponentModel.PropertyDescriptor.Equals` methods inherit the base class implementation, the change also affects these methods.</span></span>  
  
 <span data-ttu-id="3187a-105">在面向低于 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] 的 NET Framework 版本的应用中，<xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=fullName> 方法的部分相等性测试误将一个对象的 <xref:System.ComponentModel.MemberDescriptor.Category%2A?displayProperty=fullName> 属性与另一个对象的 <xref:System.ComponentModel.MemberDescriptor.Description%2A?displayProperty=fullName> 属性进行比较。</span><span class="sxs-lookup"><span data-stu-id="3187a-105">In apps that target versions of the .NET Framework prior to [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], a portion of the <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=fullName> method's test for equality  incorrectly compared the <xref:System.ComponentModel.MemberDescriptor.Category%2A?displayProperty=fullName> property of one object with the <xref:System.ComponentModel.MemberDescriptor.Description%2A?displayProperty=fullName> property of the other.</span></span> <span data-ttu-id="3187a-106">自面向 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] 的应用起，<xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=fullName> 方法比较两个对象的 <xref:System.ComponentModel.MemberDescriptor.Description%2A?displayProperty=fullName> 属性。</span><span class="sxs-lookup"><span data-stu-id="3187a-106">Starting with apps that target the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], the <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=fullName> method compares the <xref:System.ComponentModel.MemberDescriptor.Description%2A?displayProperty=fullName> property of the two objects.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="3187a-107">影响</span><span class="sxs-lookup"><span data-stu-id="3187a-107">Impact</span></span>  
 <span data-ttu-id="3187a-108">此更改正确实现了 <xref:System.ComponentModel.MemberDescriptor?displayProperty=fullName> 对象的相等性测试，造成的影响应该是最少的。</span><span class="sxs-lookup"><span data-stu-id="3187a-108">This change correctly implements the test for equality for <xref:System.ComponentModel.MemberDescriptor?displayProperty=fullName> objects and should have minimal impact.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="3187a-109">缓解操作</span><span class="sxs-lookup"><span data-stu-id="3187a-109">Mitigation</span></span>  
 <span data-ttu-id="3187a-110">如果应用面向 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] 或更高版本的 .NET Framework，并且依赖于有时在成员描述符相等时返回 `false` 的 <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=fullName> 方法，有两种解决方法可用：</span><span class="sxs-lookup"><span data-stu-id="3187a-110">Two workarounds are available if your app targets the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] or a later version of the .NET Framework and it depends on the  <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=fullName> method sometimes returning `false` when member descriptors are equivalent:</span></span>  
  
-   <span data-ttu-id="3187a-111">可以在 app.config 文件的 [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) 部分中添加下面的代码行，从而选择禁用此更改，而无需更改源代码：</span><span class="sxs-lookup"><span data-stu-id="3187a-111">You can opt out of this change without modifying your source code by adding the following to the [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of your app.config file:</span></span>  
  
    ```xml  
    <runtime>  
        <AppContextSwitchOverrides value = "Switch.System.MemberDescriptorEqualsReturnsFalseIfEquivalent=true" />  
     </runtime>  
    ```  
  
-   <span data-ttu-id="3187a-112">可通过在调用 <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=fullName> 方法后手动比较 <xref:System.ComponentModel.MemberDescriptor.Category%2A?displayProperty=fullName> 和 <xref:System.ComponentModel.MemberDescriptor.Description%2A?displayProperty=fullName> 属性，将源代码修改为还原旧行为，如以下代码片段所示。</span><span class="sxs-lookup"><span data-stu-id="3187a-112">You can modify your source code to restore the previous behavior by manually comparing the  <xref:System.ComponentModel.MemberDescriptor.Category%2A?displayProperty=fullName> and <xref:System.ComponentModel.MemberDescriptor.Description%2A?displayProperty=fullName> properties after calling the <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=fullName> method, as the following code fragment does.</span></span>  
  
    ```csharp  
    if (memberDescriptor1.Equals(memberDescriptor2) &   
        memberDescriptor1.Description.Equals(memberDescriptor2.Category)) {  
          // Code to execute if true.  
    }  
    else {  
          // Code to execute if false.     
    }  
    ```  
  
    ```  
    If memberDescriptor1.Equals(memberDescriptor2) And   
        memberDescriptor1.Description.Equals(memberDescriptor2.Category)  
          // Code to execute if True.  
    Else  
          // Code to execute if False.     
    End If  
    ```  
  
 <span data-ttu-id="3187a-113">对于定位 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] 及更低版本的应用程序，可以在 app.config 文件中添加下面的值，从而启用此更改：</span><span class="sxs-lookup"><span data-stu-id="3187a-113">For apps that target the [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] and earlier versions, you can enable this change by adding the following value to your app.config file:</span></span>  
  
```xml  
<runtime>  
    <AppContextSwitchOverrides value="Switch.System.MemberDescriptorEqualsReturnsFalseIfEquivalent=true />  
</runtime>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3187a-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3187a-114">See Also</span></span>  
 <span data-ttu-id="3187a-115">[重定目标更改](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6-2.md) </span><span class="sxs-lookup"><span data-stu-id="3187a-115">[Retargeting Changes](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6-2.md) </span></span>  
 [<span data-ttu-id="3187a-116">4.6.2 中的应用程序兼容性</span><span class="sxs-lookup"><span data-stu-id="3187a-116">Application Compatibility in 4.6.2</span></span>](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-6-2.md)

