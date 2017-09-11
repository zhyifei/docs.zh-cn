---
title: "丢失元数据异常类 (.NET Native)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 408f25c4-6d60-475c-92b1-7b52b777c6db
caps.latest.revision: 18
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 42f47b1cc184dcd789dbf38b1e5d9f03608daa04
ms.contentlocale: zh-cn
ms.lasthandoff: 08/21/2017

---
# <a name="missingmetadataexception-class-net-native"></a><span data-ttu-id="626fa-102">丢失元数据异常类 (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="626fa-102">MissingMetadataException Class (.NET Native)</span></span>
<span data-ttu-id="626fa-103">**适用于 Windows 10 的 .NET for Windows 应用，仅 [!INCLUDE[net_native](../../../includes/net-native-md.md)]**</span><span class="sxs-lookup"><span data-stu-id="626fa-103">**.NET for Windows apps for Windows 10, [!INCLUDE[net_native](../../../includes/net-native-md.md)] only**</span></span>  
  
 <span data-ttu-id="626fa-104">当反射用于检索不存在的元数据时会引起此异常。</span><span class="sxs-lookup"><span data-stu-id="626fa-104">The exception that is thrown when reflection is used to retrieve metadata that isn't present.</span></span>  
  
 <span data-ttu-id="626fa-105">命名空间：System.Reflection</span><span class="sxs-lookup"><span data-stu-id="626fa-105">**Namespace:** System.Reflection</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="626fa-106">`MissingMetadataException` 类旨在仅供 [!INCLUDE[net_native](../../../includes/net-native-md.md)] 工具链内部使用。</span><span class="sxs-lookup"><span data-stu-id="626fa-106">The `MissingMetadataException` class is intended solely for internal use by the [!INCLUDE[net_native](../../../includes/net-native-md.md)] tool chain.</span></span> <span data-ttu-id="626fa-107">它不用于在第三方代码中使用，也不应用它处理应用程序代码中的异常。</span><span class="sxs-lookup"><span data-stu-id="626fa-107">It is not intended for use in third-party code, nor should you handle the exception in your application code.</span></span> <span data-ttu-id="626fa-108">相反，你可以通过将条目添加到[运行时指令文件](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)来消除异常。</span><span class="sxs-lookup"><span data-stu-id="626fa-108">Instead, you eliminate the exception by adding entries to your [runtime directives file](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md).</span></span> <span data-ttu-id="626fa-109">有关详细信息，请参阅“备注”部分。</span><span class="sxs-lookup"><span data-stu-id="626fa-109">For more information, see the Remarks section.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="626fa-110">语法</span><span class="sxs-lookup"><span data-stu-id="626fa-110">Syntax</span></span>  
 <span data-ttu-id="626fa-111">[!code-csharp[ProjectN#4](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/missingmetadataexception_syntax1.cs#4)]</span><span class="sxs-lookup"><span data-stu-id="626fa-111">[!code-csharp[ProjectN#4](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/missingmetadataexception_syntax1.cs#4)]</span></span>  
  
 <span data-ttu-id="626fa-112">请注意，`MissingMetadataException` 类派生自 <xref:System.TypeAccessException>。</span><span class="sxs-lookup"><span data-stu-id="626fa-112">Note that the `MissingMetadataException` class derives from <xref:System.TypeAccessException>.</span></span>  
  
 <span data-ttu-id="626fa-113">`MissingMetadataException` 类包含以下成员：</span><span class="sxs-lookup"><span data-stu-id="626fa-113">The `MissingMetadataException` class has the following members:</span></span>  
  
## <a name="constructors"></a><span data-ttu-id="626fa-114">构造函数</span><span class="sxs-lookup"><span data-stu-id="626fa-114">Constructors</span></span>  
  
|<span data-ttu-id="626fa-115">构造函数</span><span class="sxs-lookup"><span data-stu-id="626fa-115">Constructor</span></span>|<span data-ttu-id="626fa-116">描述</span><span class="sxs-lookup"><span data-stu-id="626fa-116">Description</span></span>|  
|-----------------|-----------------|  
|`public MissingMetadataException()`|<span data-ttu-id="626fa-117">通过使用一个系统提供的、描述该错误的消息，来初始化 `MissingMetadataException` 类的一个实例。</span><span class="sxs-lookup"><span data-stu-id="626fa-117">Initializes a new instance of the `MissingMetadataException` class by using a system-supplied message that describes the error.</span></span><br /><br /> <span data-ttu-id="626fa-118">该构造函数仅由 [!INCLUDE[net_native](../../../includes/net-native-md.md)] 工具链用于内部用途。</span><span class="sxs-lookup"><span data-stu-id="626fa-118">This constructor is for internal use by the [!INCLUDE[net_native](../../../includes/net-native-md.md)] tool chain only.</span></span>|  
|`public MissingMetadataException(String message)`|<span data-ttu-id="626fa-119">用指定的错误消息初始化 `MissingMetadataException` 类的新实例。</span><span class="sxs-lookup"><span data-stu-id="626fa-119">Initializes a new instance of the `MissingMetadataException` class with a specified error message.</span></span><br /><br /> <span data-ttu-id="626fa-120">此构造函数仅供 [!INCLUDE[net_native](../../../includes/net-native-md.md)] 工具链内部使用。</span><span class="sxs-lookup"><span data-stu-id="626fa-120">This constructor is for internal use by the [!INCLUDE[net_native](../../../includes/net-native-md.md)] torol chain only.</span></span>|  
  
## <a name="properties"></a><span data-ttu-id="626fa-121">属性</span><span class="sxs-lookup"><span data-stu-id="626fa-121">Properties</span></span>  
  
|<span data-ttu-id="626fa-122">属性</span><span class="sxs-lookup"><span data-stu-id="626fa-122">Property</span></span>|<span data-ttu-id="626fa-123">描述</span><span class="sxs-lookup"><span data-stu-id="626fa-123">Description</span></span>|  
|--------------|-----------------|  
|`public IDictionary Data { get; }`|<span data-ttu-id="626fa-124">获取提供有关异常的其他用户定义信息的键/值对集合。</span><span class="sxs-lookup"><span data-stu-id="626fa-124">Gets a collection of key/value pairs that provide additional user-defined information about the exception.</span></span> <span data-ttu-id="626fa-125">（从 <xref:System.Exception?displayProperty=fullName> 继承。）</span><span class="sxs-lookup"><span data-stu-id="626fa-125">(Inherited from <xref:System.Exception?displayProperty=fullName>.)</span></span>|  
|`public string HelpLink { get; set; }`|<span data-ttu-id="626fa-126">获取或设置指向与此异常关联的帮助文件链接。</span><span class="sxs-lookup"><span data-stu-id="626fa-126">Gets or sets a link to the help file associated with this exception.</span></span> <span data-ttu-id="626fa-127">（从 <xref:System.Exception?displayProperty=fullName> 继承。）</span><span class="sxs-lookup"><span data-stu-id="626fa-127">(Inherited from <xref:System.Exception?displayProperty=fullName>.)</span></span>|  
|`public int HResult { get; protected set; }`|<span data-ttu-id="626fa-128">获取/设置 `HRESULT`，即分配给一个特定异常的编码数值。</span><span class="sxs-lookup"><span data-stu-id="626fa-128">Gets or sets the `HRESULT`, a coded numeric value that is assigned to a specific exception.</span></span> <span data-ttu-id="626fa-129">（从 <xref:System.Exception?displayProperty=fullName> 继承。）</span><span class="sxs-lookup"><span data-stu-id="626fa-129">(Inherited from <xref:System.Exception?displayProperty=fullName>.)</span></span>|  
|`public Exception InnerException { get; }`|<span data-ttu-id="626fa-130">获取导致当前异常的异常。</span><span class="sxs-lookup"><span data-stu-id="626fa-130">Gets the exception that caused the current exception.</span></span> <span data-ttu-id="626fa-131">（从 <xref:System.Exception?displayProperty=fullName> 继承。）</span><span class="sxs-lookup"><span data-stu-id="626fa-131">(Inherited from <xref:System.Exception?displayProperty=fullName>.)</span></span>|  
|`public string Message { get; }`|<span data-ttu-id="626fa-132">获取描述当前异常的消息。</span><span class="sxs-lookup"><span data-stu-id="626fa-132">Gets a message that describes the current exception.</span></span> <span data-ttu-id="626fa-133">（从 <xref:System.TypeLoadException> 继承。）</span><span class="sxs-lookup"><span data-stu-id="626fa-133">(Inherited from <xref:System.TypeLoadException>.)</span></span>|  
|`public string Source { get; set; }`|<span data-ttu-id="626fa-134">获取或设置导致错误的应用程序名称或对象。</span><span class="sxs-lookup"><span data-stu-id="626fa-134">Gets or sets the name of the application or object that caused the error.</span></span> <span data-ttu-id="626fa-135">（从 <xref:System.Exception?displayProperty=fullName> 继承。）</span><span class="sxs-lookup"><span data-stu-id="626fa-135">(Inherited from <xref:System.Exception?displayProperty=fullName>.)</span></span>|  
|`public string StackTrace { get; }`|<span data-ttu-id="626fa-136">获取调用堆栈上的即时框架字符串表示形式。</span><span class="sxs-lookup"><span data-stu-id="626fa-136">Gets a string representation of the immediate frames on the call stack.</span></span> <span data-ttu-id="626fa-137">（从 <xref:System.Exception?displayProperty=fullName> 继承。）</span><span class="sxs-lookup"><span data-stu-id="626fa-137">(Inherited from <xref:System.Exception?displayProperty=fullName>.)</span></span>|  
|`public MethodBase TargetSite { get; }`|<span data-ttu-id="626fa-138">获取引发当前异常的方法。</span><span class="sxs-lookup"><span data-stu-id="626fa-138">Gets the method that threw the current exception.</span></span> <span data-ttu-id="626fa-139">（从 <xref:System.Exception?displayProperty=fullName> 继承。）</span><span class="sxs-lookup"><span data-stu-id="626fa-139">(Inherited from <xref:System.Exception?displayProperty=fullName>.)</span></span>|  
|`public string TypeName { get; ]`|<span data-ttu-id="626fa-140">获取原数据丢失的类型的完全限定名称。</span><span class="sxs-lookup"><span data-stu-id="626fa-140">Gets the fully qualified name of the type whose metadata is missing.</span></span> <span data-ttu-id="626fa-141">（从 <xref:System.TypeLoadException> 继承。）</span><span class="sxs-lookup"><span data-stu-id="626fa-141">(Inherited from <xref:System.TypeLoadException>.)</span></span>|  
  
## <a name="methods"></a><span data-ttu-id="626fa-142">方法</span><span class="sxs-lookup"><span data-stu-id="626fa-142">Methods</span></span>  
  
|<span data-ttu-id="626fa-143">方法</span><span class="sxs-lookup"><span data-stu-id="626fa-143">Method</span></span>|<span data-ttu-id="626fa-144">描述</span><span class="sxs-lookup"><span data-stu-id="626fa-144">Description</span></span>|  
|------------|-----------------|  
|`public bool Equals(Object obj)`|<span data-ttu-id="626fa-145">确定指定的对象是否等于当前对象。</span><span class="sxs-lookup"><span data-stu-id="626fa-145">Determines whether the specified object is equal to the current object.</span></span>  <span data-ttu-id="626fa-146">（从 <xref:System.Exception?displayProperty=fullName> 继承。）</span><span class="sxs-lookup"><span data-stu-id="626fa-146">(Inherited from <xref:System.Exception?displayProperty=fullName>.)</span></span>|  
|`protected void Finalize()`|<span data-ttu-id="626fa-147">在垃圾回收将某一对象回收前允许该对象尝试释放资源并执行其他清理操作。</span><span class="sxs-lookup"><span data-stu-id="626fa-147">Allows an object to try to free resources and perform other cleanup operations before it is reclaimed by garbage collection.</span></span> <span data-ttu-id="626fa-148">（从 <xref:System.Object> 继承。）</span><span class="sxs-lookup"><span data-stu-id="626fa-148">(Inherited from <xref:System.Object>.)</span></span>|  
|`public Exception GetBaseException()`|<span data-ttu-id="626fa-149">返回是一个或多个后续异常的根源的异常。</span><span class="sxs-lookup"><span data-stu-id="626fa-149">Returns the exception that is the root cause of one or more subsequent exceptions.</span></span> <span data-ttu-id="626fa-150">（从 <xref:System.Exception?displayProperty=fullName> 继承。）</span><span class="sxs-lookup"><span data-stu-id="626fa-150">(Inherited from <xref:System.Exception?displayProperty=fullName>.)</span></span>|  
|`public int GetHashCode()`|<span data-ttu-id="626fa-151">为 `MissingMetadataException` 实例返回一个哈希代码。</span><span class="sxs-lookup"><span data-stu-id="626fa-151">Returns a hash code for a `MissingMetadataException` instance.</span></span>   <span data-ttu-id="626fa-152">（从 <xref:System.Object> 继承。）</span><span class="sxs-lookup"><span data-stu-id="626fa-152">(Inherited from <xref:System.Object>.)</span></span>|  
|`public void GetObjectData(SerializationInfo info, StreamingContext context)`|<span data-ttu-id="626fa-153">设置一个包含有关异常信息的 <xref:System.Runtime.Serialization.SerializationInfo> 对象。</span><span class="sxs-lookup"><span data-stu-id="626fa-153">Sets a <xref:System.Runtime.Serialization.SerializationInfo> object with information about the exception.</span></span>  <span data-ttu-id="626fa-154">（从 <xref:System.TypeLoadException> 继承。）</span><span class="sxs-lookup"><span data-stu-id="626fa-154">(Inherited from<xref:System.TypeLoadException>.)</span></span>|  
|`public Type GetType()`|<span data-ttu-id="626fa-155">获取当前实例的运行时类型。</span><span class="sxs-lookup"><span data-stu-id="626fa-155">Gets the runtime type of the current instance.</span></span> <span data-ttu-id="626fa-156">（从 <xref:System.Exception?displayProperty=fullName> 继承。）</span><span class="sxs-lookup"><span data-stu-id="626fa-156">(Inherited from <xref:System.Exception?displayProperty=fullName>.)</span></span>|  
|`protected Object MemberwiseClone()`|<span data-ttu-id="626fa-157">创建当前对象的卷影副本。</span><span class="sxs-lookup"><span data-stu-id="626fa-157">Creates a shallow copy of the current object.</span></span> <span data-ttu-id="626fa-158">（从 <xref:System.Object> 继承。）</span><span class="sxs-lookup"><span data-stu-id="626fa-158">(Inherited from <xref:System.Object>.)</span></span>|  
|`public string ToString()`|<span data-ttu-id="626fa-159">返回当前异常的字符串表示形式。</span><span class="sxs-lookup"><span data-stu-id="626fa-159">Returns the string representation of the current exception.</span></span> <span data-ttu-id="626fa-160">（从 <xref:System.Exception?displayProperty=fullName> 继承。）</span><span class="sxs-lookup"><span data-stu-id="626fa-160">(Inherited from <xref:System.Exception?displayProperty=fullName>.)</span></span>|  
  
## <a name="events"></a><span data-ttu-id="626fa-161">事件</span><span class="sxs-lookup"><span data-stu-id="626fa-161">Events</span></span>  
  
|<span data-ttu-id="626fa-162">Event</span><span class="sxs-lookup"><span data-stu-id="626fa-162">Event</span></span>|<span data-ttu-id="626fa-163">描述</span><span class="sxs-lookup"><span data-stu-id="626fa-163">Description</span></span>|  
|-----------|-----------------|  
|`protected event EventHandler<SafeSerializationEventArgs> SerializeObjectState`|<span data-ttu-id="626fa-164">当异常被序列化用来创建包含有关该异常的徐列出数据的异常状态对象时会出现该问题。</span><span class="sxs-lookup"><span data-stu-id="626fa-164">Occurs when an exception is serialized to create an exception state object that contains serialized data about the exception.</span></span> <span data-ttu-id="626fa-165">（从 <xref:System.Exception?displayProperty=fullName> 继承。）</span><span class="sxs-lookup"><span data-stu-id="626fa-165">(Inherited from <xref:System.Exception?displayProperty=fullName>.)</span></span>|  
  
## <a name="usage-details"></a><span data-ttu-id="626fa-166">使用详情</span><span class="sxs-lookup"><span data-stu-id="626fa-166">Usage Details</span></span>  
 <span data-ttu-id="626fa-167">当反射用于访问程序集中不可用的元数据时，会引起 `MissingMetadataException` 异常。</span><span class="sxs-lookup"><span data-stu-id="626fa-167">The `MissingMetadataException` exception is thrown when reflection is used to access metadata that isn’t available in an assembly.</span></span>  
  
 <span data-ttu-id="626fa-168">在运行时间一个应用可使用的元数据由运行时指令（XML 配置）文件、*.rd.xml 来定义。</span><span class="sxs-lookup"><span data-stu-id="626fa-168">The metadata that is available to an app at run time is defined by the runtime directives (XML configuration) file, *.rd.xml.</span></span> <span data-ttu-id="626fa-169">为防止应用引发此异常，应该修改\*.rd.xml 来定义在运行时间必须存在的元数据。</span><span class="sxs-lookup"><span data-stu-id="626fa-169">To prevent your app from throwing this exception, you must modify \*.rd.xml to define the metadata that must be present at run time.</span></span> <span data-ttu-id="626fa-170">有关 \*.rd.xml 文件的格式信息，请参阅[运行时指令 (rd.xml) 配置文件参考](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)。</span><span class="sxs-lookup"><span data-stu-id="626fa-170">For information about the format of the \*.rd.xml file, see [Runtime Directives (rd.xml) Configuration File Reference](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="626fa-171">由于此异常表示应用程序需要的元数据在运行时间不可用，因此不应在 `try`/`catch` 块中处理此异常。</span><span class="sxs-lookup"><span data-stu-id="626fa-171">Because this exception indicates that metadata needed by your application isn’t available at run time, you shouldn’t handle this exception in a `try`/`catch` block.</span></span> <span data-ttu-id="626fa-172">相反，你应该诊断引起此异常的原因并通过使用运行时指令文件删除它。</span><span class="sxs-lookup"><span data-stu-id="626fa-172">Instead, you should diagnose the cause of the exception and eliminate it by using a runtime directives file.</span></span> <span data-ttu-id="626fa-173">若要获取可以添加到可消除异常的运行时指令文件的项，有两个疑难解答程序可供使用：</span><span class="sxs-lookup"><span data-stu-id="626fa-173">To get the entry that you can add to your runtime directives file that eliminates the exception, you can use one of two troubleshooters:</span></span>  
>   
>  -   <span data-ttu-id="626fa-174">类型的 [MissingMetadataException 故障排除程序](http://dotnet.github.io/native/troubleshooter/type.html) 。</span><span class="sxs-lookup"><span data-stu-id="626fa-174">The [MissingMetadataException troubleshooter](http://dotnet.github.io/native/troubleshooter/type.html) for types.</span></span>  
> -   <span data-ttu-id="626fa-175">方法的 [MissingMetadataException 故障排除程序](http://dotnet.github.io/native/troubleshooter/method.html) 。</span><span class="sxs-lookup"><span data-stu-id="626fa-175">The [MissingMetadataException troubleshooter](http://dotnet.github.io/native/troubleshooter/method.html) for methods.</span></span>  
  
 <span data-ttu-id="626fa-176">`MissingMetadataException` 类不包括独有成员；它的所有成员都是从其基类即 <xref:System.TypeAccessException> 继承的。</span><span class="sxs-lookup"><span data-stu-id="626fa-176">The `MissingMetadataException` class contains no unique members; all of its members are inherited from its base class, <xref:System.TypeAccessException>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="626fa-177">另请参阅</span><span class="sxs-lookup"><span data-stu-id="626fa-177">See Also</span></span>  
 <span data-ttu-id="626fa-178"><xref:System.Exception?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="626fa-178"><xref:System.Exception?displayProperty=fullName></span></span>   
 <span data-ttu-id="626fa-179"><xref:System.TypeAccessException></span><span class="sxs-lookup"><span data-stu-id="626fa-179"><xref:System.TypeAccessException></span></span>   
 <span data-ttu-id="626fa-180">[MissingInteropDataException 类](../../../docs/framework/net-native/missinginteropdataexception-class-net-native.md) </span><span class="sxs-lookup"><span data-stu-id="626fa-180">[MissingInteropDataException Class](../../../docs/framework/net-native/missinginteropdataexception-class-net-native.md) </span></span>  
 <span data-ttu-id="626fa-181">[MissingRuntimeArtifactException 类](../../../docs/framework/net-native/missingruntimeartifactexception-class-net-native.md) </span><span class="sxs-lookup"><span data-stu-id="626fa-181">[MissingRuntimeArtifactException Class](../../../docs/framework/net-native/missingruntimeartifactexception-class-net-native.md) </span></span>  
 [<span data-ttu-id="626fa-182">运行时指令 (rd.xml) 配置文件参考</span><span class="sxs-lookup"><span data-stu-id="626fa-182">Runtime Directives (rd.xml) Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)

