---
title: "XML 序列化程序生成器工具 (Sgen.exe)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cc1d1f1c-fb26-4be9-885a-3fe84c81cec6
caps.latest.revision: "4"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 73669fcfd74f9c4948c8ec976ff3271c72f1033a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="xml-serializer-generator-tool-sgenexe"></a><span data-ttu-id="c086b-102">XML 序列化程序生成器工具 (Sgen.exe)</span><span class="sxs-lookup"><span data-stu-id="c086b-102">XML Serializer Generator Tool (Sgen.exe)</span></span>
<span data-ttu-id="c086b-103">XML 序列化程序生成器为指定程序集中的类型创建一个 XML 序列化程序集，以改进 <xref:System.Xml.Serialization.XmlSerializer> 在序列化或反序列化指定类型的对象时的启动性能。</span><span class="sxs-lookup"><span data-stu-id="c086b-103">The XML Serializer Generator creates an XML serialization assembly for types in a specified assembly in order to improve the startup performance of a <xref:System.Xml.Serialization.XmlSerializer> when it serializes or deserializes objects of the specified types.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c086b-104">语法</span><span class="sxs-lookup"><span data-stu-id="c086b-104">Syntax</span></span>  
  
```  
sgen [options]  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c086b-105">参数</span><span class="sxs-lookup"><span data-stu-id="c086b-105">Parameters</span></span>  
  
|<span data-ttu-id="c086b-106">选项</span><span class="sxs-lookup"><span data-stu-id="c086b-106">Option</span></span>|<span data-ttu-id="c086b-107">描述</span><span class="sxs-lookup"><span data-stu-id="c086b-107">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="c086b-108">**/a**[**ssembly**]**:***filename*</span><span class="sxs-lookup"><span data-stu-id="c086b-108">**/a**[**ssembly**]**:***filename*</span></span>|<span data-ttu-id="c086b-109">为由 filename 指定的程序集或可执行文件中包含的所有类型生成序列化代码。</span><span class="sxs-lookup"><span data-stu-id="c086b-109">Generates serialization code for all the types contained in the assembly or executable specified by *filename*.</span></span> <span data-ttu-id="c086b-110">只能提供一个文件名。</span><span class="sxs-lookup"><span data-stu-id="c086b-110">Only one file name can be provided.</span></span> <span data-ttu-id="c086b-111">如果该参数重复，将使用最后一个文件名。</span><span class="sxs-lookup"><span data-stu-id="c086b-111">If this argument is repeated, the last file name is used.</span></span>|  
|<span data-ttu-id="c086b-112">**/c[ompiler]:** *options*</span><span class="sxs-lookup"><span data-stu-id="c086b-112">**/c[ompiler]:** *options*</span></span>|<span data-ttu-id="c086b-113">指定要传递给 C# 编译器的选项。</span><span class="sxs-lookup"><span data-stu-id="c086b-113">Specifies the options to pass to the C# compiler.</span></span> <span data-ttu-id="c086b-114">支持所有传递到编译器的 csc.exe 选项。</span><span class="sxs-lookup"><span data-stu-id="c086b-114">All csc.exe options are supported as they are passed to the compiler.</span></span> <span data-ttu-id="c086b-115">这可用于指定应该对程序集进行签名，以及用于指定密钥文件。</span><span class="sxs-lookup"><span data-stu-id="c086b-115">This can be used to specify that the assembly should be signed and to specify the key file.</span></span>|  
|<span data-ttu-id="c086b-116">**/d**[**ebug**]</span><span class="sxs-lookup"><span data-stu-id="c086b-116">**/d**[**ebug**]</span></span>|<span data-ttu-id="c086b-117">生成一个可用于调试器的映像。</span><span class="sxs-lookup"><span data-stu-id="c086b-117">Generates an image that can be used with a debugger.</span></span>|  
|<span data-ttu-id="c086b-118">**/f[orce]**</span><span class="sxs-lookup"><span data-stu-id="c086b-118">**/f[orce]**</span></span>|<span data-ttu-id="c086b-119">强制覆盖同名的现有程序集。</span><span class="sxs-lookup"><span data-stu-id="c086b-119">Forces the overwriting of an existing assembly of the same name.</span></span> <span data-ttu-id="c086b-120">默认值为 false。</span><span class="sxs-lookup"><span data-stu-id="c086b-120">The default is **false**.</span></span>|  
|<span data-ttu-id="c086b-121">**/help 或 /?**</span><span class="sxs-lookup"><span data-stu-id="c086b-121">**/help or /?**</span></span>|<span data-ttu-id="c086b-122">显示该工具的命令语法和选项。</span><span class="sxs-lookup"><span data-stu-id="c086b-122">Displays command syntax and options for the tool.</span></span>|  
|<span data-ttu-id="c086b-123">**/k**[**eep**]</span><span class="sxs-lookup"><span data-stu-id="c086b-123">**/k**[**eep**]</span></span>|<span data-ttu-id="c086b-124">取消在生成的源文件和其他临时文件编译到序列化程序集内之后对它们的删除操作。</span><span class="sxs-lookup"><span data-stu-id="c086b-124">Suppresses the deletion of the generated source files and other temporary files after they have been compiled into the serialization assembly.</span></span> <span data-ttu-id="c086b-125">这可用于确定工具是否正在为某个特定类型生成序列化代码。</span><span class="sxs-lookup"><span data-stu-id="c086b-125">This can be used to determine whether the tool is generating serialization code for a particular type.</span></span>|  
|<span data-ttu-id="c086b-126">**/n**[**ologo**]</span><span class="sxs-lookup"><span data-stu-id="c086b-126">**/n**[**ologo**]</span></span>|<span data-ttu-id="c086b-127">取消显示 Microsoft 启动版权标志。</span><span class="sxs-lookup"><span data-stu-id="c086b-127">Suppresses the display of the Microsoft startup banner.</span></span>|  
|<span data-ttu-id="c086b-128">**/o**[**ut**]**:***path*</span><span class="sxs-lookup"><span data-stu-id="c086b-128">**/o**[**ut**]**:***path*</span></span>|<span data-ttu-id="c086b-129">指定要在其中保存生成的程序集的目录。</span><span class="sxs-lookup"><span data-stu-id="c086b-129">Specifies the directory in which to save the generated assembly.</span></span> <span data-ttu-id="c086b-130">**注意：**生成的程序集的名称由输入程序集的名称加上“xmlSerializers.dll”组成。</span><span class="sxs-lookup"><span data-stu-id="c086b-130">**Note:**  The name of the generated assembly is composed of the name of the input assembly plus "xmlSerializers.dll".</span></span>|  
|<span data-ttu-id="c086b-131">**/p**[**roxytypes**]</span><span class="sxs-lookup"><span data-stu-id="c086b-131">**/p**[**roxytypes**]</span></span>|<span data-ttu-id="c086b-132">仅生成 XML Web services 代理类型的序列化代码。</span><span class="sxs-lookup"><span data-stu-id="c086b-132">Generates serialization code only for the XML Web service proxy types.</span></span>|  
|<span data-ttu-id="c086b-133">**/r**[**eference**]**:***assemblyfiles*</span><span class="sxs-lookup"><span data-stu-id="c086b-133">**/r**[**eference**]**:***assemblyfiles*</span></span>|<span data-ttu-id="c086b-134">指定由需要 XML 序列化的类型引用的程序集。</span><span class="sxs-lookup"><span data-stu-id="c086b-134">Specifies the assemblies that are referenced by the types requiring XML serialization.</span></span> <span data-ttu-id="c086b-135">接受多个程序集文件（由逗号分隔）。</span><span class="sxs-lookup"><span data-stu-id="c086b-135">Accepts multiple assembly files separated by commas.</span></span>|  
|<span data-ttu-id="c086b-136">**/s**[**ilent**]</span><span class="sxs-lookup"><span data-stu-id="c086b-136">**/s**[**ilent**]</span></span>|<span data-ttu-id="c086b-137">取消显示成功消息。</span><span class="sxs-lookup"><span data-stu-id="c086b-137">Suppresses the display of success messages.</span></span>|  
|<span data-ttu-id="c086b-138">**/t**[**ype**]**:***type*</span><span class="sxs-lookup"><span data-stu-id="c086b-138">**/t**[**ype**]**:***type*</span></span>|<span data-ttu-id="c086b-139">仅生成指定类型的序列化代码。</span><span class="sxs-lookup"><span data-stu-id="c086b-139">Generates serialization code only for the specified type.</span></span>|  
|<span data-ttu-id="c086b-140">**/v**[**erbose**]</span><span class="sxs-lookup"><span data-stu-id="c086b-140">**/v**[**erbose**]</span></span>|<span data-ttu-id="c086b-141">显示详细输出，以进行调试。</span><span class="sxs-lookup"><span data-stu-id="c086b-141">Displays verbose output for debugging.</span></span> <span data-ttu-id="c086b-142">列出目标程序集中无法使用 <xref:System.Xml.Serialization.XmlSerializer> 进行序列化的类型。</span><span class="sxs-lookup"><span data-stu-id="c086b-142">Lists types from the target assembly that cannot be serialized with the <xref:System.Xml.Serialization.XmlSerializer>.</span></span>|  
|<span data-ttu-id="c086b-143">**/?**</span><span class="sxs-lookup"><span data-stu-id="c086b-143">**/?**</span></span>|<span data-ttu-id="c086b-144">显示该工具的命令语法和选项。</span><span class="sxs-lookup"><span data-stu-id="c086b-144">Displays command syntax and options for the tool.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c086b-145">备注</span><span class="sxs-lookup"><span data-stu-id="c086b-145">Remarks</span></span>  
 <span data-ttu-id="c086b-146">不使用 XML 序列化程序生成器时，<xref:System.Xml.Serialization.XmlSerializer> 在应用程序每次运行时为每个类型生成序列化代码和一个序列化程序集。</span><span class="sxs-lookup"><span data-stu-id="c086b-146">When the XML Serializer Generator is not used, a <xref:System.Xml.Serialization.XmlSerializer> generates serialization code and a serialization assembly for each type every time an application is run.</span></span> <span data-ttu-id="c086b-147">若要改进 XML 序列化的启动性能，请预先使用 Sgen.exe 工具生成那些程序集。</span><span class="sxs-lookup"><span data-stu-id="c086b-147">To improve the performance of XML serialization startup, use the Sgen.exe tool to generate those assemblies the assemblies in advance.</span></span> <span data-ttu-id="c086b-148">然后可以使用应用程序部署这些程序集。</span><span class="sxs-lookup"><span data-stu-id="c086b-148">These assemblies can then be deployed with the application.</span></span>  
  
 <span data-ttu-id="c086b-149">XML 序列化程序生成器还可以改进使用 XML Web services 代理与服务器通信的客户端的性能，因为在第一次加载类型时，序列化进程将不会导致性能受损。</span><span class="sxs-lookup"><span data-stu-id="c086b-149">The XML Serializer Generator can also improve the performance of clients that use XML Web service proxies to communicate with servers because the serialization process will not incur a performance hit when the type is loaded the first time.</span></span>  
  
 <span data-ttu-id="c086b-150">这些生成的程序集无法在 Web 服务的服务器端使用。</span><span class="sxs-lookup"><span data-stu-id="c086b-150">These generated assemblies cannot be used on the server side of a Web service.</span></span> <span data-ttu-id="c086b-151">该工具仅能用于 Web 服务客户端和手动序列化方案。</span><span class="sxs-lookup"><span data-stu-id="c086b-151">This tool is only for Web service clients and manual serialization scenarios.</span></span>  
  
 <span data-ttu-id="c086b-152">如果包含要序列化的类型的程序集名为 MyType.dll，则关联的序列化程序集的名称将为 MyType.XmlSerializers.dll。</span><span class="sxs-lookup"><span data-stu-id="c086b-152">If the assembly containing the type to serialize is named MyType.dll, then the associated serialization assembly will be named MyType.XmlSerializers.dll.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="c086b-153">示例</span><span class="sxs-lookup"><span data-stu-id="c086b-153">Examples</span></span>  
 <span data-ttu-id="c086b-154">下面的命令创建一个名为 Data.XmlSerializers.dll 的程序集，用于序列化名为 Data.dll 的程序集中包含的所有类型。</span><span class="sxs-lookup"><span data-stu-id="c086b-154">The following command creates an assembly named Data.XmlSerializers.dll for serializing all the types contained in the assembly named Data.dll.</span></span>  
  
```  
sgen Data.dll   
```  
  
 <span data-ttu-id="c086b-155">可以从代码中引用需要序列化和反序列化 Data.dll 中的类型的 Data.XmlSerializers.dll 程序集。</span><span class="sxs-lookup"><span data-stu-id="c086b-155">The Data.XmlSerializers.dll assembly can be referenced from code that needs to serialize and deserialize the types in Data.dll.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c086b-156">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c086b-156">See Also</span></span>  
 [<span data-ttu-id="c086b-157">工具</span><span class="sxs-lookup"><span data-stu-id="c086b-157">Tools</span></span>](../../../docs/framework/tools/index.md)  
 [<span data-ttu-id="c086b-158">XML Web 服务概述</span><span class="sxs-lookup"><span data-stu-id="c086b-158">XML Web Services Overview</span></span>](http://msdn.microsoft.com/en-us/9db0c7b8-bca6-462b-9be5-f5f9a7f05a4d)  
 [<span data-ttu-id="c086b-159">命令提示</span><span class="sxs-lookup"><span data-stu-id="c086b-159">Command Prompts</span></span>](../../../docs/framework/tools/developer-command-prompt-for-vs.md)
