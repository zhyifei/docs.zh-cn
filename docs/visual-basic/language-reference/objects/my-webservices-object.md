---
title: My.WebServices 对象 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- My.WebServices
- My.MyProject.WebServices
helpviewer_keywords:
- My.WebServices object
ms.assetid: f188dc05-2c75-41b6-bb68-122d1c3110a2
ms.openlocfilehash: a60f32c4f581e42f240fca55ce496776c5511ba3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "58840427"
---
# <a name="mywebservices-object"></a><span data-ttu-id="8d9fc-102">My.WebServices 对象</span><span class="sxs-lookup"><span data-stu-id="8d9fc-102">My.WebServices Object</span></span>
<span data-ttu-id="8d9fc-103">提供用于创建和访问当前项目所引用的每个 XML Web 服务的单个实例的属性。</span><span class="sxs-lookup"><span data-stu-id="8d9fc-103">Provides properties for creating and accessing a single instance of each XML Web service referenced by the current project.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8d9fc-104">备注</span><span class="sxs-lookup"><span data-stu-id="8d9fc-104">Remarks</span></span>  
 <span data-ttu-id="8d9fc-105">`My.WebServices` 对象提供当前项目所引用的每个 Web 服务的实例。</span><span class="sxs-lookup"><span data-stu-id="8d9fc-105">The `My.WebServices` object provides an instance of each Web service referenced by the current project.</span></span> <span data-ttu-id="8d9fc-106">按需实例化每个实例。</span><span class="sxs-lookup"><span data-stu-id="8d9fc-106">Each instance is instantiated on demand.</span></span> <span data-ttu-id="8d9fc-107">可以通过 `My.WebServices` 对象的属性访问这些 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="8d9fc-107">You can access these Web services through the properties of the `My.WebServices` object.</span></span> <span data-ttu-id="8d9fc-108">该属性的名称与该属性所访问的 Web 服务的名称相同。</span><span class="sxs-lookup"><span data-stu-id="8d9fc-108">The name of the property is the same as the name of the Web service that the property accesses.</span></span> <span data-ttu-id="8d9fc-109">任何自 <xref:System.Web.Services.Protocols.SoapHttpClientProtocol> 继承的类均为 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="8d9fc-109">Any class that inherits from <xref:System.Web.Services.Protocols.SoapHttpClientProtocol> is a Web service.</span></span> <span data-ttu-id="8d9fc-110">有关将 Web 服务添加到项目的信息，请参阅[访问应用程序 Web 服务](../../../visual-basic/developing-apps/programming/accessing-application-web-services.md)。</span><span class="sxs-lookup"><span data-stu-id="8d9fc-110">For information about adding Web services to a project, see [Accessing Application Web Services](../../../visual-basic/developing-apps/programming/accessing-application-web-services.md).</span></span>  
  
 <span data-ttu-id="8d9fc-111">`My.WebServices`对象公开的与当前项目相关联的 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="8d9fc-111">The `My.WebServices` object exposes only the Web services associated with the current project.</span></span> <span data-ttu-id="8d9fc-112">它不提供对被引用的 Dll 中声明的 Web 服务的访问。</span><span class="sxs-lookup"><span data-stu-id="8d9fc-112">It does not provide access to Web services declared in referenced DLLs.</span></span> <span data-ttu-id="8d9fc-113">若要访问 DLL 提供的 Web 服务，必须使用 Web 服务的限定的名形式*DllName*。*WebServiceName*。</span><span class="sxs-lookup"><span data-stu-id="8d9fc-113">To access a Web service that a DLL provides, you must use the qualified name of the Web service, in the form *DllName*.*WebServiceName*.</span></span> <span data-ttu-id="8d9fc-114">有关详细信息，请参阅[访问应用程序 Web 服务](../../../visual-basic/developing-apps/programming/accessing-application-web-services.md)。</span><span class="sxs-lookup"><span data-stu-id="8d9fc-114">For more information, see [Accessing Application Web Services](../../../visual-basic/developing-apps/programming/accessing-application-web-services.md).</span></span>  
  
 <span data-ttu-id="8d9fc-115">对象和其属性不适用于 Web 应用程序。</span><span class="sxs-lookup"><span data-stu-id="8d9fc-115">The object and its properties are not available for Web applications.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="8d9fc-116">属性</span><span class="sxs-lookup"><span data-stu-id="8d9fc-116">Properties</span></span>  
 <span data-ttu-id="8d9fc-117">每个属性`My.WebServices`对象提供对当前项目所引用的 Web 服务的实例访问。</span><span class="sxs-lookup"><span data-stu-id="8d9fc-117">Each property of the `My.WebServices` object provides access to an instance of a Web service referenced by the current project.</span></span> <span data-ttu-id="8d9fc-118">属性的名称访问该属性，Web 服务的名称相同，属性类型是 Web 服务的类型相同。</span><span class="sxs-lookup"><span data-stu-id="8d9fc-118">The name of the property is the same as the name of the Web service that the property accesses, and the property type is the same as the Web service's type.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8d9fc-119">如果没有名称冲突，用于访问 Web 服务的属性名称是*RootNamespace*_*Namespace*\_*ServiceName*。</span><span class="sxs-lookup"><span data-stu-id="8d9fc-119">If there is a name collision, the property name for accessing a Web service is *RootNamespace*_*Namespace*\_*ServiceName*.</span></span> <span data-ttu-id="8d9fc-120">例如，考虑名为两个 Web 服务`Service1`。</span><span class="sxs-lookup"><span data-stu-id="8d9fc-120">For example, consider two Web services named `Service1`.</span></span> <span data-ttu-id="8d9fc-121">如果这些服务之一就是根命名空间`WindowsApplication1`和命名空间中`Namespace1`，将使用访问该服务`My.WebServices.WindowsApplication1_Namespace1_Service1`。</span><span class="sxs-lookup"><span data-stu-id="8d9fc-121">If one of these services is in the root namespace `WindowsApplication1` and in the namespace `Namespace1`, you would access that service by using `My.WebServices.WindowsApplication1_Namespace1_Service1`.</span></span>  
  
 <span data-ttu-id="8d9fc-122">当首次访问之一`My.WebServices`对象的属性，它将创建 Web 服务的新实例并将其存储。</span><span class="sxs-lookup"><span data-stu-id="8d9fc-122">When you first access one of the `My.WebServices` object's properties, it creates a new instance of the Web service and stores it.</span></span> <span data-ttu-id="8d9fc-123">该属性的后续访问返回的 Web 服务的实例。</span><span class="sxs-lookup"><span data-stu-id="8d9fc-123">Subsequent accesses of that property return that instance of the Web service.</span></span>  
  
 <span data-ttu-id="8d9fc-124">您可以通过将分配释放 Web 服务的`Nothing`到该 Web 服务的属性。</span><span class="sxs-lookup"><span data-stu-id="8d9fc-124">You can dispose of a Web service by assigning `Nothing` to the property for that Web service.</span></span> <span data-ttu-id="8d9fc-125">属性 setter 将分配`Nothing`与存储的值。</span><span class="sxs-lookup"><span data-stu-id="8d9fc-125">The property setter assigns `Nothing` to the stored value.</span></span> <span data-ttu-id="8d9fc-126">如果不是将任何值赋`Nothing`与属性 setter 引发<xref:System.ArgumentException>异常。</span><span class="sxs-lookup"><span data-stu-id="8d9fc-126">If you assign any value other than `Nothing` to the property, the setter throws an <xref:System.ArgumentException> exception.</span></span>  
  
 <span data-ttu-id="8d9fc-127">你可以测试的属性是否`My.WebServices`对象将 Web 服务的实例存储通过使用`Is`或`IsNot`运算符。</span><span class="sxs-lookup"><span data-stu-id="8d9fc-127">You can test whether a property of the `My.WebServices` object stores an instance of the Web service by using the `Is` or `IsNot` operator.</span></span> <span data-ttu-id="8d9fc-128">可以使用这些运算符来检查属性的值是否为`Nothing`。</span><span class="sxs-lookup"><span data-stu-id="8d9fc-128">You can use those operators to check if the value of the property is `Nothing`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8d9fc-129">通常情况下，`Is`或`IsNot`操作员必须读取的属性进行比较的值。</span><span class="sxs-lookup"><span data-stu-id="8d9fc-129">Typically, the `Is` or `IsNot` operator has to read the value of the property to perform the comparison.</span></span> <span data-ttu-id="8d9fc-130">但是，如果该属性将当前存储`Nothing`，该属性创建 Web 服务的新实例，然后返回该实例。</span><span class="sxs-lookup"><span data-stu-id="8d9fc-130">However, if the property currently stores `Nothing`, the property creates a new instance of the Web service and then returns that instance.</span></span> <span data-ttu-id="8d9fc-131">但是，Visual Basic 编译器处理的属性`My.WebServices`对象，并允许`Is`或`IsNot`运算符来检查属性的状态，而无需更改其值。</span><span class="sxs-lookup"><span data-stu-id="8d9fc-131">However, the Visual Basic compiler treats the properties of the `My.WebServices` object specially, and allows the `Is` or `IsNot` operator to check the status of the property without altering its value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8d9fc-132">示例</span><span class="sxs-lookup"><span data-stu-id="8d9fc-132">Example</span></span>  
 <span data-ttu-id="8d9fc-133">此示例调用`FahrenheitToCelsius`方法的`TemperatureConverter`XML Web 服务，并返回结果。</span><span class="sxs-lookup"><span data-stu-id="8d9fc-133">This example calls the `FahrenheitToCelsius` method of the `TemperatureConverter` XML Web service, and returns the result.</span></span>  
  
 [!code-vb[VbVbalrMyWebService#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyWebService/VB/Form1.vb#1)]  
  
 <span data-ttu-id="8d9fc-134">此示例正常工作，为你的项目必须引用一个名为 Web 服务`Converter`，并且该 Web 服务必须公开`ConvertTemperature`方法。</span><span class="sxs-lookup"><span data-stu-id="8d9fc-134">For this example to work, your project must reference a Web service named `Converter`, and that Web service must expose the `ConvertTemperature` method.</span></span> <span data-ttu-id="8d9fc-135">有关详细信息，请参阅[访问应用程序 Web 服务](../../../visual-basic/developing-apps/programming/accessing-application-web-services.md)。</span><span class="sxs-lookup"><span data-stu-id="8d9fc-135">For more information, see [Accessing Application Web Services](../../../visual-basic/developing-apps/programming/accessing-application-web-services.md).</span></span>  
  
 <span data-ttu-id="8d9fc-136">此代码不适用于 Web 应用程序项目。</span><span class="sxs-lookup"><span data-stu-id="8d9fc-136">This code does not work in a Web application project.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8d9fc-137">要求</span><span class="sxs-lookup"><span data-stu-id="8d9fc-137">Requirements</span></span>  
  
### <a name="availability-by-project-type"></a><span data-ttu-id="8d9fc-138">项目类型的可用性</span><span class="sxs-lookup"><span data-stu-id="8d9fc-138">Availability by Project Type</span></span>  
  
|<span data-ttu-id="8d9fc-139">项目类型</span><span class="sxs-lookup"><span data-stu-id="8d9fc-139">Project type</span></span>|<span data-ttu-id="8d9fc-140">可用</span><span class="sxs-lookup"><span data-stu-id="8d9fc-140">Available</span></span>|  
|---|---|  
|<span data-ttu-id="8d9fc-141">Windows 应用程序</span><span class="sxs-lookup"><span data-stu-id="8d9fc-141">Windows Application</span></span>|<span data-ttu-id="8d9fc-142">**是**</span><span class="sxs-lookup"><span data-stu-id="8d9fc-142">**Yes**</span></span>|  
|<span data-ttu-id="8d9fc-143">类库</span><span class="sxs-lookup"><span data-stu-id="8d9fc-143">Class Library</span></span>|<span data-ttu-id="8d9fc-144">**是**</span><span class="sxs-lookup"><span data-stu-id="8d9fc-144">**Yes**</span></span>|  
|<span data-ttu-id="8d9fc-145">控制台应用程序</span><span class="sxs-lookup"><span data-stu-id="8d9fc-145">Console Application</span></span>|<span data-ttu-id="8d9fc-146">**是**</span><span class="sxs-lookup"><span data-stu-id="8d9fc-146">**Yes**</span></span>|  
|<span data-ttu-id="8d9fc-147">Windows 控件库</span><span class="sxs-lookup"><span data-stu-id="8d9fc-147">Windows Control Library</span></span>|<span data-ttu-id="8d9fc-148">**是**</span><span class="sxs-lookup"><span data-stu-id="8d9fc-148">**Yes**</span></span>|  
|<span data-ttu-id="8d9fc-149">Web 控件库</span><span class="sxs-lookup"><span data-stu-id="8d9fc-149">Web Control Library</span></span>|<span data-ttu-id="8d9fc-150">**是**</span><span class="sxs-lookup"><span data-stu-id="8d9fc-150">**Yes**</span></span>|  
|<span data-ttu-id="8d9fc-151">Windows 服务</span><span class="sxs-lookup"><span data-stu-id="8d9fc-151">Windows Service</span></span>|<span data-ttu-id="8d9fc-152">**是**</span><span class="sxs-lookup"><span data-stu-id="8d9fc-152">**Yes**</span></span>|  
|<span data-ttu-id="8d9fc-153">网站</span><span class="sxs-lookup"><span data-stu-id="8d9fc-153">Web Site</span></span>|<span data-ttu-id="8d9fc-154">否</span><span class="sxs-lookup"><span data-stu-id="8d9fc-154">No</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8d9fc-155">请参阅</span><span class="sxs-lookup"><span data-stu-id="8d9fc-155">See also</span></span>

- <xref:System.Web.Services.Protocols.SoapHttpClientProtocol>
- <xref:System.ArgumentException>
- [<span data-ttu-id="8d9fc-156">访问应用程序 Web 服务</span><span class="sxs-lookup"><span data-stu-id="8d9fc-156">Accessing Application Web Services</span></span>](../../../visual-basic/developing-apps/programming/accessing-application-web-services.md)
