---
title: XML 序列化程序生成器工具 (Sgen.exe)
ms.date: 03/30/2017
ms.assetid: cc1d1f1c-fb26-4be9-885a-3fe84c81cec6
ms.openlocfilehash: bc1a0abaeef9a9244aa83941e590063c7ef167d1
ms.sourcegitcommit: 961ec21c22d2f1d55c9cc8a7edf2ade1d1fd92e3
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2020
ms.locfileid: "80588361"
---
# <a name="xml-serializer-generator-tool-sgenexe"></a><span data-ttu-id="509df-102">XML 序列化程序生成器工具 (Sgen.exe)</span><span class="sxs-lookup"><span data-stu-id="509df-102">XML Serializer Generator Tool (Sgen.exe)</span></span>

<span data-ttu-id="509df-103">XML 序列化程序生成器创建指定程序集中的类型的 XML 序列化程序集。</span><span class="sxs-lookup"><span data-stu-id="509df-103">The XML Serializer Generator creates an XML serialization assembly for types in a specified assembly.</span></span> <span data-ttu-id="509df-104">序列化程序集在序列化或反序列化指定类型的对象时，将改进 <xref:System.Xml.Serialization.XmlSerializer> 的启动性能。</span><span class="sxs-lookup"><span data-stu-id="509df-104">The serialization assembly improves the startup performance of a <xref:System.Xml.Serialization.XmlSerializer> when it serializes or deserializes objects of the specified types.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="509df-105">语法</span><span class="sxs-lookup"><span data-stu-id="509df-105">Syntax</span></span>

<span data-ttu-id="509df-106">从命令行运行该工具。</span><span class="sxs-lookup"><span data-stu-id="509df-106">Run the tool from the command line.</span></span>
  
```console  
sgen [options]  
```
  
> [!TIP]
> <span data-ttu-id="509df-107">要使 .NET Framework 工具正常发挥作用，必须正确设置 `Path`、`Include` 和 `Lib` 环境变量。</span><span class="sxs-lookup"><span data-stu-id="509df-107">For .NET Framework tools to function properly, you must set your `Path`, `Include`, and `Lib` environment variables correctly.</span></span> <span data-ttu-id="509df-108">可以通过运行 SDKVars.bat（位于 \<SDK>\v2.0\Bin 目录中）来设置这些环境变量。</span><span class="sxs-lookup"><span data-stu-id="509df-108">Set these environment variables by running SDKVars.bat, which is located in the \<SDK>\v2.0\Bin directory.</span></span> <span data-ttu-id="509df-109">必须在每个命令 shell 程序中执行 SDKVars.bat。</span><span class="sxs-lookup"><span data-stu-id="509df-109">SDKVars.bat must be executed in every command shell.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="509df-110">参数</span><span class="sxs-lookup"><span data-stu-id="509df-110">Parameters</span></span>  
  
|<span data-ttu-id="509df-111">选项</span><span class="sxs-lookup"><span data-stu-id="509df-111">Option</span></span>|<span data-ttu-id="509df-112">描述</span><span class="sxs-lookup"><span data-stu-id="509df-112">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="509df-113">**/a\[ssembly\]:** _filename_</span><span class="sxs-lookup"><span data-stu-id="509df-113">**/a\[ssembly\]:**_filename_</span></span>|<span data-ttu-id="509df-114">为由 filename 指定的程序集或可执行文件中包含的所有类型生成序列化代码  。</span><span class="sxs-lookup"><span data-stu-id="509df-114">Generates serialization code for all the types contained in the assembly or executable specified by *filename*.</span></span> <span data-ttu-id="509df-115">只能提供一个文件名。</span><span class="sxs-lookup"><span data-stu-id="509df-115">Only one file name can be provided.</span></span> <span data-ttu-id="509df-116">如果该参数重复，将使用最后一个文件名。</span><span class="sxs-lookup"><span data-stu-id="509df-116">If this argument is repeated, the last file name is used.</span></span>|  
|<span data-ttu-id="509df-117">**/c\[ompiler\]:** _options_</span><span class="sxs-lookup"><span data-stu-id="509df-117">**/c\[ompiler\]:**_options_</span></span>|<span data-ttu-id="509df-118">指定要传递给 C# 编译器的选项。</span><span class="sxs-lookup"><span data-stu-id="509df-118">Specifies the options to pass to the C# compiler.</span></span> <span data-ttu-id="509df-119">支持所有传递到编译器的 csc.exe 选项。</span><span class="sxs-lookup"><span data-stu-id="509df-119">All csc.exe options are supported as they are passed to the compiler.</span></span> <span data-ttu-id="509df-120">这可用于指定应该对程序集进行签名，以及用于指定密钥文件。</span><span class="sxs-lookup"><span data-stu-id="509df-120">This can be used to specify that the assembly should be signed and to specify the key file.</span></span>|  
|<span data-ttu-id="509df-121">**/d\[ebug\]**</span><span class="sxs-lookup"><span data-stu-id="509df-121">**/d\[ebug\]**</span></span>|<span data-ttu-id="509df-122">生成一个可用于调试器的映像。</span><span class="sxs-lookup"><span data-stu-id="509df-122">Generates an image that can be used with a debugger.</span></span>|  
|<span data-ttu-id="509df-123">**/f\[orce\]**</span><span class="sxs-lookup"><span data-stu-id="509df-123">**/f\[orce\]**</span></span>|<span data-ttu-id="509df-124">强制覆盖同名的现有程序集。</span><span class="sxs-lookup"><span data-stu-id="509df-124">Forces the overwriting of an existing assembly of the same name.</span></span> <span data-ttu-id="509df-125">默认值为 false  。</span><span class="sxs-lookup"><span data-stu-id="509df-125">The default is **false**.</span></span>|  
|<span data-ttu-id="509df-126">**/help 或 /?**</span><span class="sxs-lookup"><span data-stu-id="509df-126">**/help or /?**</span></span>|<span data-ttu-id="509df-127">显示该工具的命令语法和选项。</span><span class="sxs-lookup"><span data-stu-id="509df-127">Displays command syntax and options for the tool.</span></span>|  
|<span data-ttu-id="509df-128">**/k\[eep\]**</span><span class="sxs-lookup"><span data-stu-id="509df-128">**/k\[eep\]**</span></span>|<span data-ttu-id="509df-129">取消在生成的源文件和其他临时文件编译到序列化程序集内之后对它们的删除操作。</span><span class="sxs-lookup"><span data-stu-id="509df-129">Suppresses the deletion of the generated source files and other temporary files after they have been compiled into the serialization assembly.</span></span> <span data-ttu-id="509df-130">这可用于确定工具是否正在为某个特定类型生成序列化代码。</span><span class="sxs-lookup"><span data-stu-id="509df-130">This can be used to determine whether the tool is generating serialization code for a particular type.</span></span>|  
|<span data-ttu-id="509df-131">**/n\[ologo\]**</span><span class="sxs-lookup"><span data-stu-id="509df-131">**/n\[ologo\]**</span></span>|<span data-ttu-id="509df-132">取消显示 Microsoft 启动版权标志。</span><span class="sxs-lookup"><span data-stu-id="509df-132">Suppresses the display of the Microsoft startup banner.</span></span>|  
|<span data-ttu-id="509df-133">**/o\[ut\]:** _path_</span><span class="sxs-lookup"><span data-stu-id="509df-133">**/o\[ut\]:**_path_</span></span>|<span data-ttu-id="509df-134">指定要在其中保存生成的程序集的目录。</span><span class="sxs-lookup"><span data-stu-id="509df-134">Specifies the directory in which to save the generated assembly.</span></span> <span data-ttu-id="509df-135">**注意：** 生成的程序集的名称由输入程序集的名称加上“xmlSerializers.dll”组成。</span><span class="sxs-lookup"><span data-stu-id="509df-135">**Note:**  The name of the generated assembly is composed of the name of the input assembly plus "xmlSerializers.dll".</span></span>|  
|<span data-ttu-id="509df-136">**/p\[roxytypes\]**</span><span class="sxs-lookup"><span data-stu-id="509df-136">**/p\[roxytypes\]**</span></span>|<span data-ttu-id="509df-137">仅生成 XML Web services 代理类型的序列化代码。</span><span class="sxs-lookup"><span data-stu-id="509df-137">Generates serialization code only for the XML Web service proxy types.</span></span>|  
|<span data-ttu-id="509df-138">**/r\[eference\]:** _assemblyfiles_</span><span class="sxs-lookup"><span data-stu-id="509df-138">**/r\[eference\]:**_assemblyfiles_</span></span>|<span data-ttu-id="509df-139">指定由需要 XML 序列化的类型引用的程序集。</span><span class="sxs-lookup"><span data-stu-id="509df-139">Specifies the assemblies that are referenced by the types requiring XML serialization.</span></span> <span data-ttu-id="509df-140">接受多个程序集文件（由逗号分隔）。</span><span class="sxs-lookup"><span data-stu-id="509df-140">Accepts multiple assembly files separated by commas.</span></span>|  
|<span data-ttu-id="509df-141">**/s\[ilent\]**</span><span class="sxs-lookup"><span data-stu-id="509df-141">**/s\[ilent\]**</span></span>|<span data-ttu-id="509df-142">取消显示成功消息。</span><span class="sxs-lookup"><span data-stu-id="509df-142">Suppresses the display of success messages.</span></span>|  
|<span data-ttu-id="509df-143">**/t\[ype\]:** _type_</span><span class="sxs-lookup"><span data-stu-id="509df-143">**/t\[ype\]:**_type_</span></span>|<span data-ttu-id="509df-144">仅生成指定类型的序列化代码。</span><span class="sxs-lookup"><span data-stu-id="509df-144">Generates serialization code only for the specified type.</span></span>|  
|<span data-ttu-id="509df-145">**/v\[erbose\]**</span><span class="sxs-lookup"><span data-stu-id="509df-145">**/v\[erbose\]**</span></span>|<span data-ttu-id="509df-146">显示详细输出，以进行调试。</span><span class="sxs-lookup"><span data-stu-id="509df-146">Displays verbose output for debugging.</span></span> <span data-ttu-id="509df-147">列出目标程序集中无法使用 <xref:System.Xml.Serialization.XmlSerializer> 进行序列化的类型。</span><span class="sxs-lookup"><span data-stu-id="509df-147">Lists types from the target assembly that cannot be serialized with the <xref:System.Xml.Serialization.XmlSerializer>.</span></span>|  
|<span data-ttu-id="509df-148">**/?**</span><span class="sxs-lookup"><span data-stu-id="509df-148">**/?**</span></span>|<span data-ttu-id="509df-149">显示该工具的命令语法和选项。</span><span class="sxs-lookup"><span data-stu-id="509df-149">Displays command syntax and options for the tool.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="509df-150">备注</span><span class="sxs-lookup"><span data-stu-id="509df-150">Remarks</span></span>  
 <span data-ttu-id="509df-151">不使用 XML 序列化程序生成器时，<xref:System.Xml.Serialization.XmlSerializer> 在应用程序每次运行时为每个类型生成序列化代码和一个序列化程序集。</span><span class="sxs-lookup"><span data-stu-id="509df-151">When the XML Serializer Generator is not used, a <xref:System.Xml.Serialization.XmlSerializer> generates serialization code and a serialization assembly for each type every time an application is run.</span></span> <span data-ttu-id="509df-152">若要改进 XML 序列化的启动性能，请预先使用 Sgen.exe 工具生成那些程序集。</span><span class="sxs-lookup"><span data-stu-id="509df-152">To improve the performance of XML serialization startup, use the Sgen.exe tool to generate those assemblies in advance.</span></span> <span data-ttu-id="509df-153">然后可以使用应用程序部署这些程序集。</span><span class="sxs-lookup"><span data-stu-id="509df-153">These assemblies can then be deployed with the application.</span></span>  
  
 <span data-ttu-id="509df-154">XML 序列化程序生成器还可以改进使用 XML Web services 代理与服务器通信的客户端的性能，因为在第一次加载类型时，序列化进程将不会导致性能受损。</span><span class="sxs-lookup"><span data-stu-id="509df-154">The XML Serializer Generator can also improve the performance of clients that use XML Web service proxies to communicate with servers because the serialization process will not incur a performance hit when the type is loaded the first time.</span></span>  
  
 <span data-ttu-id="509df-155">这些生成的程序集无法在 Web 服务的服务器端使用。</span><span class="sxs-lookup"><span data-stu-id="509df-155">These generated assemblies cannot be used on the server side of a Web service.</span></span> <span data-ttu-id="509df-156">该工具仅能用于 Web 服务客户端和手动序列化方案。</span><span class="sxs-lookup"><span data-stu-id="509df-156">This tool is only for Web service clients and manual serialization scenarios.</span></span>  
  
 <span data-ttu-id="509df-157">如果包含要序列化的类型的程序集名为 MyType.dll，则关联的序列化程序集的名称将为 MyType.XmlSerializers.dll。</span><span class="sxs-lookup"><span data-stu-id="509df-157">If the assembly containing the type to serialize is named MyType.dll, then the associated serialization assembly will be named MyType.XmlSerializers.dll.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="509df-158">示例</span><span class="sxs-lookup"><span data-stu-id="509df-158">Examples</span></span>  
 <span data-ttu-id="509df-159">下面的命令创建一个名为 Data.XmlSerializers.dll 的程序集，用于序列化名为 Data.dll 的程序集中包含的所有类型。</span><span class="sxs-lookup"><span data-stu-id="509df-159">The following command creates an assembly named Data.XmlSerializers.dll for serializing all the types contained in the assembly named Data.dll.</span></span>  
  
```console  
sgen Data.dll
```  
  
 <span data-ttu-id="509df-160">可以从代码中引用需要序列化和反序列化 Data.dll 中的类型的 Data.XmlSerializers.dll 程序集。</span><span class="sxs-lookup"><span data-stu-id="509df-160">The Data.XmlSerializers.dll assembly can be referenced from code that needs to serialize and deserialize the types in Data.dll.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="509df-161">请参阅</span><span class="sxs-lookup"><span data-stu-id="509df-161">See also</span></span>

- [<span data-ttu-id="509df-162">工具</span><span class="sxs-lookup"><span data-stu-id="509df-162">Tools</span></span>](../../../docs/framework/tools/index.md)
- [<span data-ttu-id="509df-163">命令提示</span><span class="sxs-lookup"><span data-stu-id="509df-163">Command Prompts</span></span>](../../../docs/framework/tools/developer-command-prompt-for-vs.md)
