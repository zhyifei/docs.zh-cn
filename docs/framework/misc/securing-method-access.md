---
title: 保护方法访问
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- code security, method access
- secure coding, method access
- security [.NET Framework], method access
- method access security
ms.assetid: f7c2d6ec-3b18-4e0e-9991-acd97189d818
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2159199fc12ef83a6bf4a44841d71799e0dad4dc
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59166174"
---
# <a name="securing-method-access"></a><span data-ttu-id="af4ea-102">保护方法访问</span><span class="sxs-lookup"><span data-stu-id="af4ea-102">Securing Method Access</span></span>
[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]  
  
 <span data-ttu-id="af4ea-103">某些方法可能不适用于允许任意不受信任的代码进行调用。</span><span class="sxs-lookup"><span data-stu-id="af4ea-103">Some methods might not be suitable to allow arbitrary untrusted code to call.</span></span> <span data-ttu-id="af4ea-104">此类方法会带来几种风险：该方法可能会提供一些受限制的信息;它可能信任传递给它; 的任何信息它可能不会执行错误检查的参数;或使用错误的参数，它可能会出现故障或执行某些有害操作。</span><span class="sxs-lookup"><span data-stu-id="af4ea-104">Such methods pose several risks: The method might provide some restricted information; it might believe any information passed to it; it might not do error checking on the parameters; or with the wrong parameters, it might malfunction or do something harmful.</span></span> <span data-ttu-id="af4ea-105">应该注意这些情况，并采取措施以帮助保护这类方法。</span><span class="sxs-lookup"><span data-stu-id="af4ea-105">You should be aware of these cases and take action to help protect the method.</span></span>  
  
 <span data-ttu-id="af4ea-106">在某些情况下，可能需要限制并不打算用于公共用途但仍须为公共方法的方法。</span><span class="sxs-lookup"><span data-stu-id="af4ea-106">In some cases, you might need to restrict methods that are not intended for public use but still must be public.</span></span> <span data-ttu-id="af4ea-107">例如，可能有一个需在你自己的 DLL 间调用（从而必须为公共接口）的接口，但你不希望将其以公共方式公开，以防止客户使用它，或防止恶意代码利用入口点进入组件中。</span><span class="sxs-lookup"><span data-stu-id="af4ea-107">For example, you might have an interface that needs to be called across your own DLLs and hence must be public, but you do not want to expose it publicly to prevent customers from using it or to prevent malicious code from exploiting the entry point into your component.</span></span> <span data-ttu-id="af4ea-108">限制不打算用于公共用途（但必须为公共方法）的方法的另一个常见理由是：为了避免不得不记录和支持可能是内部接口的接口。</span><span class="sxs-lookup"><span data-stu-id="af4ea-108">Another common reason to restrict a method not intended for public use (but that must be public) is to avoid having to document and support what might be a very internal interface.</span></span>  
  
 <span data-ttu-id="af4ea-109">托管代码提供几种方法来限制方法访问：</span><span class="sxs-lookup"><span data-stu-id="af4ea-109">Managed code offers several ways to restrict method access:</span></span>  
  
-   <span data-ttu-id="af4ea-110">如果可以信任类、程序集或派生类，则限制它们的可访问性的范围。</span><span class="sxs-lookup"><span data-stu-id="af4ea-110">Limit the scope of accessibility to the class, assembly, or derived classes, if they can be trusted.</span></span> <span data-ttu-id="af4ea-111">这是限制方法访问的最简单的方法。</span><span class="sxs-lookup"><span data-stu-id="af4ea-111">This is the simplest way to limit method access.</span></span> <span data-ttu-id="af4ea-112">请注意，派生类的可信度通常可低于其从中派生的类，尽管在某些情况下它们共享父类的标识。</span><span class="sxs-lookup"><span data-stu-id="af4ea-112">Note that, in general, derived classes can be less trustworthy than the class they derive from, though in some cases they share the parent class's identity.</span></span> <span data-ttu-id="af4ea-113">具体而言，不推断从关键字**保护**，这不一定使用的安全上下文中。</span><span class="sxs-lookup"><span data-stu-id="af4ea-113">In particular, do not infer trust from the keyword **protected**, which is not necessarily used in the security context.</span></span>  
  
-   <span data-ttu-id="af4ea-114">限制对指定的标识-从根本上讲，任何特定的调用方的方法访问[证据](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7y5x1hcd%28v=vs.100%29)选择 （强名称、 发布服务器、 区域等）。</span><span class="sxs-lookup"><span data-stu-id="af4ea-114">Limit the method access to callers of a specified identity--essentially, any particular [evidence](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7y5x1hcd%28v=vs.100%29) (strong name, publisher, zone, and so on) you choose.</span></span>  
  
-   <span data-ttu-id="af4ea-115">限制对具有你选择的任何权限的调用方的方法访问。</span><span class="sxs-lookup"><span data-stu-id="af4ea-115">Limit the method access to callers having whatever permissions you select.</span></span>  
  
 <span data-ttu-id="af4ea-116">同样，声明性安全使你可以控制类的继承。</span><span class="sxs-lookup"><span data-stu-id="af4ea-116">Similarly, declarative security allows you to control inheritance of classes.</span></span> <span data-ttu-id="af4ea-117">可以使用**InheritanceDemand**来执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="af4ea-117">You can use **InheritanceDemand** to do the following:</span></span>  
  
-   <span data-ttu-id="af4ea-118">要求派生类具有指定的标识或权限。</span><span class="sxs-lookup"><span data-stu-id="af4ea-118">Require derived classes to have a specified identity or permission.</span></span>  
  
-   <span data-ttu-id="af4ea-119">要求重写特定方法的派生类具有指定的标识或权限。</span><span class="sxs-lookup"><span data-stu-id="af4ea-119">Require derived classes that override specific methods to have a specified identity or permission.</span></span>  
  
 <span data-ttu-id="af4ea-120">下面的示例演示如何通过要求使用特定强名称对调用方进行签名来帮助保护具有有限访问权限的公共类。</span><span class="sxs-lookup"><span data-stu-id="af4ea-120">The following example shows how to help protect a public class for limited access by requiring that callers be signed with a particular strong name.</span></span> <span data-ttu-id="af4ea-121">此示例使用<xref:System.Security.Permissions.StrongNameIdentityPermissionAttribute>与**需**为强名称。</span><span class="sxs-lookup"><span data-stu-id="af4ea-121">This example uses the <xref:System.Security.Permissions.StrongNameIdentityPermissionAttribute> with a **Demand** for the strong name.</span></span> <span data-ttu-id="af4ea-122">有关如何为程序集具有强名称签名的基于任务的信息，请参阅[创建和使用具有强名称程序集](../../../docs/framework/app-domains/create-and-use-strong-named-assemblies.md)。</span><span class="sxs-lookup"><span data-stu-id="af4ea-122">For task-based information on how to sign an assembly with a strong name, see [Creating and Using Strong-Named Assemblies](../../../docs/framework/app-domains/create-and-use-strong-named-assemblies.md).</span></span>  
  
```vb  
<StrongNameIdentityPermissionAttribute(SecurityAction.Demand, PublicKey := "…hex…", Name := "App1", Version := "0.0.0.0")>  _  
Public Class Class1  
End Class  
```  
  
```csharp  
[StrongNameIdentityPermissionAttribute(SecurityAction.Demand, PublicKey="…hex…", Name="App1", Version="0.0.0.0")]  
public class Class1  
{  
  
}   
```  
  
## <a name="excluding-classes-and-members-from-use-by-untrusted-code"></a><span data-ttu-id="af4ea-123">防止不受信任的代码使用类和成员</span><span class="sxs-lookup"><span data-stu-id="af4ea-123">Excluding Classes and Members from Use by Untrusted Code</span></span>  
 <span data-ttu-id="af4ea-124">使用本节中所示的声明来防止部分受信任的代码使用特定的类、方法以及属性和事件。</span><span class="sxs-lookup"><span data-stu-id="af4ea-124">Use the declarations shown in this section to prevent specific classes and methods, as well as properties and events, from being used by partially trusted code.</span></span> <span data-ttu-id="af4ea-125">将这些声明应用到类，即可对类的所有方法、属性和事件应用保护；但请注意，字段访问不受声明性安全影响。</span><span class="sxs-lookup"><span data-stu-id="af4ea-125">By applying these declarations to a class, you apply the protection to all its methods, properties, and events; however, note that field access is not affected by declarative security.</span></span> <span data-ttu-id="af4ea-126">也请注意，链接要求仅帮助不受直接调用方的攻击，可能仍会受到引诱攻击。</span><span class="sxs-lookup"><span data-stu-id="af4ea-126">Note also that link demands help protect against only the immediate callers and might still be subject to luring attacks.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="af4ea-127">[!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] 中引入了新的透明度模型。</span><span class="sxs-lookup"><span data-stu-id="af4ea-127">A new transparency model has been introduced in the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)].</span></span> <span data-ttu-id="af4ea-128">[安全透明的代码，级别 2](../../../docs/framework/misc/security-transparent-code-level-2.md)模型标识安全代码与<xref:System.Security.SecurityCriticalAttribute>属性。</span><span class="sxs-lookup"><span data-stu-id="af4ea-128">The [Security-Transparent Code, Level 2](../../../docs/framework/misc/security-transparent-code-level-2.md) model identifies secure code with the <xref:System.Security.SecurityCriticalAttribute> attribute.</span></span> <span data-ttu-id="af4ea-129">安全关键代码需要调用方和继承者均完全受信任。</span><span class="sxs-lookup"><span data-stu-id="af4ea-129">Security-critical code requires both callers and inheritors to be fully trusted.</span></span> <span data-ttu-id="af4ea-130">在早期 .NET Framework 版本中的代码访问安全性规则下运行的程序集可以调用级别 2 程序集。</span><span class="sxs-lookup"><span data-stu-id="af4ea-130">Assemblies that are running under the code access security rules from earlier .NET Framework versions can call level 2 assemblies.</span></span> <span data-ttu-id="af4ea-131">在这种情况下，安全关键属性将被视为完全信任的链接要求。</span><span class="sxs-lookup"><span data-stu-id="af4ea-131">In this case, the security-critical attributes will be treated as link demands for full trust.</span></span>  
  
 <span data-ttu-id="af4ea-132">在强名称的程序集中[LinkDemand](../../../docs/framework/misc/link-demands.md)应用于所有可以访问的方法、 属性和其中到完全受信任调用方限制其使用的事件。</span><span class="sxs-lookup"><span data-stu-id="af4ea-132">In strong-named assemblies, a [LinkDemand](../../../docs/framework/misc/link-demands.md) is applied to all publicly accessible methods, properties, and events therein to restrict their use to fully trusted callers.</span></span> <span data-ttu-id="af4ea-133">若要禁用此功能，必须应用 <xref:System.Security.AllowPartiallyTrustedCallersAttribute> 特性。</span><span class="sxs-lookup"><span data-stu-id="af4ea-133">To disable this feature, you must apply the <xref:System.Security.AllowPartiallyTrustedCallersAttribute> attribute.</span></span> <span data-ttu-id="af4ea-134">因此，仅未签名的程序集或具有此特性的程序集需要显式标记类以排除不受信任调用方；可以使用这些声明来标记其中并不打算用于不受信任的调用方的类型子集。</span><span class="sxs-lookup"><span data-stu-id="af4ea-134">Thus, explicitly marking classes to exclude untrusted callers is necessary only for unsigned assemblies or assemblies with this attribute; you can use these declarations to mark a subset of types therein that are not intended for untrusted callers.</span></span>  
  
 <span data-ttu-id="af4ea-135">下面的示例说明如何防止不受信任的代码使用类和成员。</span><span class="sxs-lookup"><span data-stu-id="af4ea-135">The following examples show how to prevent classes and members from being used by untrusted code.</span></span>  
  
 <span data-ttu-id="af4ea-136">对于公共非密封类：</span><span class="sxs-lookup"><span data-stu-id="af4ea-136">For public nonsealed classes:</span></span>  
  
```vb  
<System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.InheritanceDemand, Name := "FullTrust"), _   
System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name := "FullTrust")>  _  
Public Class CanDeriveFromMe  
End Class  
```  
  
```csharp  
[System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.InheritanceDemand, Name="FullTrust")]  
[System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name="FullTrust")]  
public class CanDeriveFromMe  
{  
}  
```  
  
 <span data-ttu-id="af4ea-137">对于公共密封类：</span><span class="sxs-lookup"><span data-stu-id="af4ea-137">For public sealed classes:</span></span>  
  
```vb  
<System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name := "FullTrust")>  _  
NotInheritable Public Class CannotDeriveFromMe  
End Class  
```  
  
```csharp  
[System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name="FullTrust")]  
public sealed class CannotDeriveFromMe  
{  
}  
```  
  
 <span data-ttu-id="af4ea-138">对于公共抽象类：</span><span class="sxs-lookup"><span data-stu-id="af4ea-138">For public abstract classes:</span></span>  
  
```vb  
<System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.InheritanceDemand, Name := "FullTrust"), _  
System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name := "FullTrust")>  _  
MustInherit Public Class CannotCreateInstanceOfMe_CanCastToMe  
End Class  
```  
  
```csharp  
[System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.InheritanceDemand, Name="FullTrust")]  
[System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name="FullTrust")]  
public abstract class CannotCreateInstanceOfMe_CanCastToMe {}  
```  
  
 <span data-ttu-id="af4ea-139">对于公共虚拟函数：</span><span class="sxs-lookup"><span data-stu-id="af4ea-139">For public virtual functions:</span></span>  
  
```vb  
Class Base1   
<System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.InheritanceDemand, Name:="FullTrust"), System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name:="FullTrust")> _  
    Public Overridable Sub CanOverrideOrCallMe()  
    End Sub 'CanOverrideOrCallMe  
End Class 'Base1  
```  
  
```csharp  
class Base1   
{  
[System.Security.Permissions.PermissionSetAttribute(  
System.Security.Permissions.SecurityAction.InheritanceDemand, Name="FullTrust")]  
[System.Security.Permissions.PermissionSetAttribute(  
System.Security.Permissions.SecurityAction.LinkDemand, Name="FullTrust")]  
    public virtual void CanOverrideOrCallMe() {}  
}  
```  
  
 <span data-ttu-id="af4ea-140">对于公共抽象函数：</span><span class="sxs-lookup"><span data-stu-id="af4ea-140">For public abstract functions:</span></span>  
  
```vb  
MustInherit Class Base2  
    <System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.InheritanceDemand, Name:="FullTrust"), System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name:="FullTrust")> _  
    Public Sub MustOverrideMe()  
    End Sub  
End Class 'Base2  
```  
  
```csharp  
abstract class Base2 {  
[System.Security.Permissions.PermissionSetAttribute(  
System.Security.Permissions.SecurityAction.InheritanceDemand, Name = "FullTrust")]  
[System.Security.Permissions.PermissionSetAttribute(  
System.Security.Permissions.SecurityAction.LinkDemand, Name = "FullTrust")]  
public abstract void MustOverrideMe();  
}  
```  
  
 <span data-ttu-id="af4ea-141">对于基类不要求完全信任的公共重写函数：</span><span class="sxs-lookup"><span data-stu-id="af4ea-141">For public override functions where the base class does not demand full trust:</span></span>  
  
```vb  
Class Derived  
    Inherits Base1  
<System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.Demand, Name:="FullTrust")> _  
    Public Overrides Sub CanOverrideOrCallMe()  
        MyBase.CanOverrideOrCallMe()  
    End Sub 'CanOverrideOrCallMe  
End Class 'Derived  
```  
  
```csharp  
class Derived : Base1  
{     
[System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.Demand, Name="FullTrust")]      
    public override void CanOverrideOrCallMe()   
    {  
        base.CanOverrideOrCallMe();  
    }  
}  
```  
  
 <span data-ttu-id="af4ea-142">对于基类要求完全信任的公共重写函数：</span><span class="sxs-lookup"><span data-stu-id="af4ea-142">For public override functions where the base class demands full trust:</span></span>  
  
```vb  
Class Derived  
    Inherits Base1  
<System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name:="FullTrust")> _  
    Public Overrides Sub CanOverrideOrCallMe()  
        MyBase.CanOverrideOrCallMe()  
    End Sub 'CanOverrideOrCallMe   
End Class 'Derived  
```  
  
```csharp  
class Derived : Base1  
{     
[System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name="FullTrust")]      
    public override void CanOverrideOrCallMe()   
    {  
        base.CanOverrideOrCallMe();  
    }  
}  
```  
  
 <span data-ttu-id="af4ea-143">对于公共接口：</span><span class="sxs-lookup"><span data-stu-id="af4ea-143">For public interfaces:</span></span>  
  
```vb  
Public Interface ICanCastToMe  
    <System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name:="FullTrust"), System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.InheritanceDemand, Name:="FullTrust")> _  
    Sub CanImplementMe()  
End Interface 'ICanCastToMe  
<System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name:="FullTrust"), System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.InheritanceDemand, Name:="FullTrust")> _  
Class Implemented  
    Implements ICanCastToMe  
    Public Sub CanImplementMe()  
    End Sub 'CanImplementMe  
```  
  
```csharp  
public interface ICanCastToMe   
{  
[System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name = "FullTrust")]  
[System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.InheritanceDemand, Name = "FullTrust")]  
void CanImplementMe();  
}  
[System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name = "FullTrust")]  
[System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.InheritanceDemand, Name = "FullTrust")]  
class Implemented : ICanCastToMe  
{  
    public void CanImplementMe()  
    {  
    }  
}  
```  
  
## <a name="virtual-internal-overrides-or-overloads-overridable-friend"></a><span data-ttu-id="af4ea-144">Virtual Internal 重写或 Overloads Overridable Friend</span><span class="sxs-lookup"><span data-stu-id="af4ea-144">Virtual Internal Overrides or Overloads Overridable Friend</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="af4ea-145">本部分中的安全问题时将方法声明为同时发出警告`virtual`并`internal`(`Overloads` `Overridable` `Friend`在 Visual Basic 中)。</span><span class="sxs-lookup"><span data-stu-id="af4ea-145">This section warns about a security issue when declaring a method as both `virtual` and `internal` (`Overloads` `Overridable` `Friend` in Visual Basic).</span></span> <span data-ttu-id="af4ea-146">此警告仅适用于.NET framework 1.0 和 1.1 版，不适用于更高版本。</span><span class="sxs-lookup"><span data-stu-id="af4ea-146">This warning applies only to the .NET Framework versions 1.0 and 1.1, it does not apply to later versions.</span></span>  
  
 <span data-ttu-id="af4ea-147">在.NET framework 1.0 和 1.1 版中，您必须注意类型系统可访问性的细微差别时确认你的代码对其他程序集不可用。</span><span class="sxs-lookup"><span data-stu-id="af4ea-147">In the .NET Framework versions 1.0 and 1.1, you must be aware of a nuance of the type system accessibility when confirming that your code is unavailable to other assemblies.</span></span> <span data-ttu-id="af4ea-148">声明的方法**虚拟**并**内部**(**Overloads Overridable Friend**在 Visual Basic 中) 可以重写父类的 vtable 条目，并可以仅通过使用在同一程序集中因为它是内部。</span><span class="sxs-lookup"><span data-stu-id="af4ea-148">A method that is declared **virtual** and **internal** (**Overloads Overridable Friend** in Visual Basic) can override the parent class's vtable entry and can be used only from within the same assembly because it is internal.</span></span> <span data-ttu-id="af4ea-149">但是，由重写的可访问性**虚拟**关键字，并且可以覆盖从另一个程序集，只要该代码有权访问类本身。</span><span class="sxs-lookup"><span data-stu-id="af4ea-149">However, the accessibility for overriding is determined by the **virtual** keyword, and this can be overridden from another assembly as long as that code has access to the class itself.</span></span> <span data-ttu-id="af4ea-150">如果重写可能会出现问题，使用声明性安全来解决问题，或删除**虚拟**如果不是绝对必需的关键字。</span><span class="sxs-lookup"><span data-stu-id="af4ea-150">If the possibility of an override presents a problem, use declarative security to fix it, or remove the **virtual** keyword if it is not strictly required.</span></span>  
  
 <span data-ttu-id="af4ea-151">请注意，即使语言编译器通过编译错误防止这些重写，使用其他编译器编写的代码也可能发生重写。</span><span class="sxs-lookup"><span data-stu-id="af4ea-151">Note that even if a language compiler prevents these overrides with a compilation error, it is possible for code written with other compilers to override.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af4ea-152">请参阅</span><span class="sxs-lookup"><span data-stu-id="af4ea-152">See also</span></span>

- [<span data-ttu-id="af4ea-153">代码安全维护指南</span><span class="sxs-lookup"><span data-stu-id="af4ea-153">Secure Coding Guidelines</span></span>](../../../docs/standard/security/secure-coding-guidelines.md)
