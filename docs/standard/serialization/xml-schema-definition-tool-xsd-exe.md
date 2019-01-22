---
title: XML Schema Definition Tool (Xsd.exe)
ms.date: 03/30/2017
ms.assetid: a6e6e65c-347f-4494-9457-653bf29baac2
ms.openlocfilehash: a7824f0f39820b186b654aa4369dc068134d6a0d
ms.sourcegitcommit: 42522983167b52852e1a20c87d57a1f63215f9bd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2019
ms.locfileid: "54443650"
---
# <a name="xml-schema-definition-tool-xsdexe"></a><span data-ttu-id="e7bc1-102">XML Schema Definition Tool (Xsd.exe)</span><span class="sxs-lookup"><span data-stu-id="e7bc1-102">XML Schema Definition Tool (Xsd.exe)</span></span>
<span data-ttu-id="e7bc1-103">XML 架构定义 (Xsd.exe) 工具从 XDR、XML 和 XSD 文件或者从运行时程序集中的类生成 XML 架构或公共语言运行时类。</span><span class="sxs-lookup"><span data-stu-id="e7bc1-103">The XML Schema Definition (Xsd.exe) tool generates XML schema or common language runtime classes from XDR, XML, and XSD files, or from classes in a runtime assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7bc1-104">语法</span><span class="sxs-lookup"><span data-stu-id="e7bc1-104">Syntax</span></span>  
  
```  
xsd file.xdr [/outputdir:directory][/parameters:file.xml]  
xsd file.xml [/outputdir:directory] [/parameters:file.xml]  
xsd file.xsd {/classes | /dataset} [/element:element]   
             [/enableLinqDataSet] [/language:language]   
                          [/namespace:namespace] [/outputdir:directory] [URI:uri]   
                          [/parameters:file.xml]  
xsd {file.dll | file.exe} [/outputdir:directory] [/type:typename [...]][/parameters:file.xml]  
```  
  
## <a name="argument"></a><span data-ttu-id="e7bc1-105">参数</span><span class="sxs-lookup"><span data-stu-id="e7bc1-105">Argument</span></span>  
  
|<span data-ttu-id="e7bc1-106">参数</span><span class="sxs-lookup"><span data-stu-id="e7bc1-106">Argument</span></span>|<span data-ttu-id="e7bc1-107">描述</span><span class="sxs-lookup"><span data-stu-id="e7bc1-107">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="e7bc1-108">file.extension</span><span class="sxs-lookup"><span data-stu-id="e7bc1-108">*file.extension*</span></span>|<span data-ttu-id="e7bc1-109">指定要转换的输入文件。</span><span class="sxs-lookup"><span data-stu-id="e7bc1-109">Specifies the input file to convert.</span></span> <span data-ttu-id="e7bc1-110">必须将扩展名指定为下列之一：.xdr、.xml、.xsd、.dll 或 .exe。</span><span class="sxs-lookup"><span data-stu-id="e7bc1-110">You must specify the extensionas one of the following: .xdr, .xml, .xsd, .dll, or .exe.</span></span><br /><br /> <span data-ttu-id="e7bc1-111">如果指定一个 XDR 架构文件（.xdr 扩展名），则 Xsd.exe 将 XDR 架构转换为 XSD 架构。</span><span class="sxs-lookup"><span data-stu-id="e7bc1-111">If you specify an XDR schema file (.xdr extension), Xsd.exe converts the XDR schema to an XSD schema.</span></span> <span data-ttu-id="e7bc1-112">输出文件与 XDR 架构同名，但扩展名为 .xsd。</span><span class="sxs-lookup"><span data-stu-id="e7bc1-112">The output file has the same name as the XDR schema, but with the .xsd extension.</span></span><br /><br /> <span data-ttu-id="e7bc1-113">如果指定一个 XML 文件（.xml 扩展名），则 Xsd.exe 从文件中的数据推导出架构并产生一个 XSD 架构。</span><span class="sxs-lookup"><span data-stu-id="e7bc1-113">If you specify an XML file (.xml extension), Xsd.exe infers a schema from the data in the file and produces an XSD schema.</span></span> <span data-ttu-id="e7bc1-114">输出文件与 XML 文件同名，但扩展名为 .xsd。</span><span class="sxs-lookup"><span data-stu-id="e7bc1-114">The output file has the same name as the XML file, but with the .xsd extension.</span></span><br /><br /> <span data-ttu-id="e7bc1-115">如果指定一个 XML 架构文件（.xsd 扩展名），则 Xsd.exe 将为对应于 XML 架构的运行时对象生成源代码。</span><span class="sxs-lookup"><span data-stu-id="e7bc1-115">If you specify an XML schema file (.xsd extension), Xsd.exe generates source code for runtime objects that correspond to the XML schema.</span></span><br /><br /> <span data-ttu-id="e7bc1-116">如果指定一个运行时程序集文件（.exe 或 .dll 扩展名），则 Xsd.exe 为该程序集中的一个或多个类型生成架构。</span><span class="sxs-lookup"><span data-stu-id="e7bc1-116">If you specify a runtime assembly file (.exe or .dll extension), Xsd.exe generates schemas for one or more types in that assembly.</span></span> <span data-ttu-id="e7bc1-117">可以使用 `/type` 选项来指定为其生成架构的类型。</span><span class="sxs-lookup"><span data-stu-id="e7bc1-117">You can use the `/type` option to specify the types for which to generate schemas.</span></span> <span data-ttu-id="e7bc1-118">输出架构被命名为 schema0.xsd、schema1.xsd，依此类推。</span><span class="sxs-lookup"><span data-stu-id="e7bc1-118">The output schemas are named schema0.xsd, schema1.xsd, and so on.</span></span> <span data-ttu-id="e7bc1-119">仅当给定类型使用 `XMLRoot` 自定义特性指定命名空间时，Xsd.exe 才生成多个架构。</span><span class="sxs-lookup"><span data-stu-id="e7bc1-119">Xsd.exe produces multiple schemas only if the given types specify a namespace using the `XMLRoot` custom attribute.</span></span>|  
  
## <a name="general-options"></a><span data-ttu-id="e7bc1-120">常规选项</span><span class="sxs-lookup"><span data-stu-id="e7bc1-120">General Options</span></span>  
  
|<span data-ttu-id="e7bc1-121">选项</span><span class="sxs-lookup"><span data-stu-id="e7bc1-121">Option</span></span>|<span data-ttu-id="e7bc1-122">描述</span><span class="sxs-lookup"><span data-stu-id="e7bc1-122">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="e7bc1-123">**/h\[elp\]**</span><span class="sxs-lookup"><span data-stu-id="e7bc1-123">**/h\[elp\]**</span></span>|<span data-ttu-id="e7bc1-124">显示该工具的命令语法和选项。</span><span class="sxs-lookup"><span data-stu-id="e7bc1-124">Displays command syntax and options for the tool.</span></span>|  
|<span data-ttu-id="e7bc1-125">**/o\[utputdir\]:**_directory_</span><span class="sxs-lookup"><span data-stu-id="e7bc1-125">**/o\[utputdir\]:**_directory_</span></span>|<span data-ttu-id="e7bc1-126">指定输出文件的目录。</span><span class="sxs-lookup"><span data-stu-id="e7bc1-126">Specifies the directory for output files.</span></span> <span data-ttu-id="e7bc1-127">此参数只能出现一次。</span><span class="sxs-lookup"><span data-stu-id="e7bc1-127">This argument can appear only once.</span></span> <span data-ttu-id="e7bc1-128">默认为当前目录。</span><span class="sxs-lookup"><span data-stu-id="e7bc1-128">The default is the current directory.</span></span>|  
|<span data-ttu-id="e7bc1-129">**/?**</span><span class="sxs-lookup"><span data-stu-id="e7bc1-129">**/?**</span></span>|<span data-ttu-id="e7bc1-130">显示该工具的命令语法和选项。</span><span class="sxs-lookup"><span data-stu-id="e7bc1-130">Displays command syntax and options for the tool.</span></span>|  
|<span data-ttu-id="e7bc1-131">**/p\[arameters\]:**_file.xml_</span><span class="sxs-lookup"><span data-stu-id="e7bc1-131">**/p\[arameters\]:**_file.xml_</span></span>|<span data-ttu-id="e7bc1-132">从指定的 .xml 文件读取各种操作模式的选项。</span><span class="sxs-lookup"><span data-stu-id="e7bc1-132">Read options for various operation modes from the specified .xml file.</span></span> <span data-ttu-id="e7bc1-133">缩写形式为 `/p:`。</span><span class="sxs-lookup"><span data-stu-id="e7bc1-133">The short form is `/p:`.</span></span> <span data-ttu-id="e7bc1-134">有关详细信息，请参阅[备注](#remarks)部分。</span><span class="sxs-lookup"><span data-stu-id="e7bc1-134">For more information, see the [Remarks](#remarks) section.</span></span>|  
  
## <a name="xsd-file-options"></a><span data-ttu-id="e7bc1-135">XSD 文件选项</span><span class="sxs-lookup"><span data-stu-id="e7bc1-135">XSD File Options</span></span>  
 <span data-ttu-id="e7bc1-136">必须为 xsd 文件仅指定下列选项中的一个。</span><span class="sxs-lookup"><span data-stu-id="e7bc1-136">You must specify only one of the following options for .xsd files.</span></span>  
  
|<span data-ttu-id="e7bc1-137">选项</span><span class="sxs-lookup"><span data-stu-id="e7bc1-137">Option</span></span>|<span data-ttu-id="e7bc1-138">描述</span><span class="sxs-lookup"><span data-stu-id="e7bc1-138">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="e7bc1-139">**/c\[lasses\]**</span><span class="sxs-lookup"><span data-stu-id="e7bc1-139">**/c\[lasses\]**</span></span>|<span data-ttu-id="e7bc1-140">生成与指定架构相对应的类。</span><span class="sxs-lookup"><span data-stu-id="e7bc1-140">Generates classes that correspond to the specified schema.</span></span> <span data-ttu-id="e7bc1-141">若要将 XML 数据读入对象中，请使用 <xref:System.Xml.Serialization.XmlSerializer.Deserialize%2A?displayProperty=nameWithType> 方法。</span><span class="sxs-lookup"><span data-stu-id="e7bc1-141">To read XML data into the object, use the <xref:System.Xml.Serialization.XmlSerializer.Deserialize%2A?displayProperty=nameWithType> method.</span></span>|  
|<span data-ttu-id="e7bc1-142">**/d[ataset]**</span><span class="sxs-lookup"><span data-stu-id="e7bc1-142">**/d[ataset]**</span></span>|<span data-ttu-id="e7bc1-143">生成一个从 <xref:System.Data.DataSet> 派生的类，该类与指定的架构相对应。</span><span class="sxs-lookup"><span data-stu-id="e7bc1-143">Generates a class derived from <xref:System.Data.DataSet> that corresponds to the specified schema.</span></span> <span data-ttu-id="e7bc1-144">若要将 XML 数据读入派生类中，请使用 <xref:System.Data.DataSet.ReadXml%2A?displayProperty=nameWithType> 方法。</span><span class="sxs-lookup"><span data-stu-id="e7bc1-144">To read XML data into the derived class, use the <xref:System.Data.DataSet.ReadXml%2A?displayProperty=nameWithType> method.</span></span>|  
  
 <span data-ttu-id="e7bc1-145">还可以为 .xsd 文件指定下列任何选项。</span><span class="sxs-lookup"><span data-stu-id="e7bc1-145">You can also specify any of the following options for .xsd files.</span></span>  
  
|<span data-ttu-id="e7bc1-146">选项</span><span class="sxs-lookup"><span data-stu-id="e7bc1-146">Option</span></span>|<span data-ttu-id="e7bc1-147">描述</span><span class="sxs-lookup"><span data-stu-id="e7bc1-147">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="e7bc1-148">**/e\[lement\]:**_element_</span><span class="sxs-lookup"><span data-stu-id="e7bc1-148">**/e\[lement\]:**_element_</span></span>|<span data-ttu-id="e7bc1-149">指定架构中要为其生成代码的元素。</span><span class="sxs-lookup"><span data-stu-id="e7bc1-149">Specifies the element in the schema to generate code for.</span></span> <span data-ttu-id="e7bc1-150">默认情况下，键入所有元素。</span><span class="sxs-lookup"><span data-stu-id="e7bc1-150">By default all elements are typed.</span></span> <span data-ttu-id="e7bc1-151">可以多次指定该参数。</span><span class="sxs-lookup"><span data-stu-id="e7bc1-151">You can specify this argument more than once.</span></span>|  
|<span data-ttu-id="e7bc1-152">**/enableDataBinding**</span><span class="sxs-lookup"><span data-stu-id="e7bc1-152">**/enableDataBinding**</span></span>|<span data-ttu-id="e7bc1-153">在所有生成的类型上实现 <xref:System.ComponentModel.INotifyPropertyChanged> 接口以启用数据绑定。</span><span class="sxs-lookup"><span data-stu-id="e7bc1-153">Implements the <xref:System.ComponentModel.INotifyPropertyChanged> interface on all generated types to enable data binding.</span></span> <span data-ttu-id="e7bc1-154">缩写形式为 `/edb`。</span><span class="sxs-lookup"><span data-stu-id="e7bc1-154">The short form is `/edb`.</span></span>|  
|<span data-ttu-id="e7bc1-155">**/enableLinqDataSet**</span><span class="sxs-lookup"><span data-stu-id="e7bc1-155">**/enableLinqDataSet**</span></span>|<span data-ttu-id="e7bc1-156">（缩写形式：`/eld`。）指定可使用 LINQ to DataSet 查询的生成的数据集。</span><span class="sxs-lookup"><span data-stu-id="e7bc1-156">(Short form: `/eld`.) Specifies that the generated DataSet can be queried against using LINQ to DataSet.</span></span> <span data-ttu-id="e7bc1-157">此选项在同时指定 /dataset 选项的情况下使用。</span><span class="sxs-lookup"><span data-stu-id="e7bc1-157">This option is used when the /dataset option is also specified.</span></span> <span data-ttu-id="e7bc1-158">有关详细信息，请参阅 [LINQ to DataSet 概述](../../../docs/framework/data/adonet/linq-to-dataset-overview.md)和[查询类型化数据集](../../../docs/framework/data/adonet/querying-typed-datasets.md)。</span><span class="sxs-lookup"><span data-stu-id="e7bc1-158">For more information, see [LINQ to DataSet Overview](../../../docs/framework/data/adonet/linq-to-dataset-overview.md) and [Querying Typed DataSets](../../../docs/framework/data/adonet/querying-typed-datasets.md).</span></span> <span data-ttu-id="e7bc1-159">有关使用 LINQ 的一般信息，请参阅 [LINQ（语言集成查询）](https://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d)。</span><span class="sxs-lookup"><span data-stu-id="e7bc1-159">For general information about using LINQ, see [LINQ (Language-Integrated Query)](https://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d).</span></span>|  
|<span data-ttu-id="e7bc1-160">**/f\[ields\]**</span><span class="sxs-lookup"><span data-stu-id="e7bc1-160">**/f\[ields\]**</span></span>|<span data-ttu-id="e7bc1-161">生成字段，而不是生成属性。</span><span class="sxs-lookup"><span data-stu-id="e7bc1-161">Generates fields instead of properties.</span></span> <span data-ttu-id="e7bc1-162">默认情况下生成属性。</span><span class="sxs-lookup"><span data-stu-id="e7bc1-162">By default, properties are generated.</span></span>|  
|<span data-ttu-id="e7bc1-163">**/l\[anguage\]:**_language_</span><span class="sxs-lookup"><span data-stu-id="e7bc1-163">**/l\[anguage\]:**_language_</span></span>|<span data-ttu-id="e7bc1-164">指定要使用的编程语言。</span><span class="sxs-lookup"><span data-stu-id="e7bc1-164">Specifies the programming language to use.</span></span> <span data-ttu-id="e7bc1-165">从 `CS`（默认情况下为 C#）、`VB` (Visual Basic)、`JS` (JScript) 或 `VJS` (Visual J#) 中进行选择。</span><span class="sxs-lookup"><span data-stu-id="e7bc1-165">Choose from `CS` (C#, which is the default), `VB` (Visual Basic), `JS` (JScript), or `VJS` (Visual J#).</span></span> <span data-ttu-id="e7bc1-166">也可指定实现 <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType> 的类的完全限定名</span><span class="sxs-lookup"><span data-stu-id="e7bc1-166">You can also specify a fully qualified name for a class implementing <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType></span></span>|  
|<span data-ttu-id="e7bc1-167">**/n\[amespace\]:**_namespace_</span><span class="sxs-lookup"><span data-stu-id="e7bc1-167">**/n\[amespace\]:**_namespace_</span></span>|<span data-ttu-id="e7bc1-168">为生成的类型指定运行时命名空间。</span><span class="sxs-lookup"><span data-stu-id="e7bc1-168">Specifies the runtime namespace for the generated types.</span></span> <span data-ttu-id="e7bc1-169">默认命名空间为 `Schemas`。</span><span class="sxs-lookup"><span data-stu-id="e7bc1-169">The default namespace is `Schemas`.</span></span>|  
|<span data-ttu-id="e7bc1-170">**/nologo**</span><span class="sxs-lookup"><span data-stu-id="e7bc1-170">**/nologo**</span></span>|<span data-ttu-id="e7bc1-171">取消显示版权标志。</span><span class="sxs-lookup"><span data-stu-id="e7bc1-171">Suppresses the banner.</span></span>|  
|<span data-ttu-id="e7bc1-172">**/order**</span><span class="sxs-lookup"><span data-stu-id="e7bc1-172">**/order**</span></span>|<span data-ttu-id="e7bc1-173">在所有粒子成员上生成显式顺序标识符。</span><span class="sxs-lookup"><span data-stu-id="e7bc1-173">Generates explicit order identifiers on all particle members.</span></span>|  
|<span data-ttu-id="e7bc1-174">**/o\[ut\]:**_directoryName_</span><span class="sxs-lookup"><span data-stu-id="e7bc1-174">**/o\[ut\]:**_directoryName_</span></span>|<span data-ttu-id="e7bc1-175">指定用来放置文件的输出目录。</span><span class="sxs-lookup"><span data-stu-id="e7bc1-175">Specifies the output directory to place the files in.</span></span> <span data-ttu-id="e7bc1-176">默认为当前目录。</span><span class="sxs-lookup"><span data-stu-id="e7bc1-176">The default is the current directory.</span></span>|  
|<span data-ttu-id="e7bc1-177">**/u\[ri\]:**_uri_</span><span class="sxs-lookup"><span data-stu-id="e7bc1-177">**/u\[ri\]:**_uri_</span></span>|<span data-ttu-id="e7bc1-178">为架构中要为其生成代码的元素指定 URI。</span><span class="sxs-lookup"><span data-stu-id="e7bc1-178">Specifies the URI for the elements in the schema to generate code for.</span></span> <span data-ttu-id="e7bc1-179">该 URI（如果存在）应用于使用 `/element` 选项指定的所有元素。</span><span class="sxs-lookup"><span data-stu-id="e7bc1-179">This URI, if present, applies to all elements specified with the `/element` option.</span></span>|  
  
## <a name="dll-and-exe-file-options"></a><span data-ttu-id="e7bc1-180">DLL 和 EXE 文件选项</span><span class="sxs-lookup"><span data-stu-id="e7bc1-180">DLL and EXE File Options</span></span>  
  
|<span data-ttu-id="e7bc1-181">选项</span><span class="sxs-lookup"><span data-stu-id="e7bc1-181">Option</span></span>|<span data-ttu-id="e7bc1-182">描述</span><span class="sxs-lookup"><span data-stu-id="e7bc1-182">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="e7bc1-183">**/t\[ype\]:**_typename_</span><span class="sxs-lookup"><span data-stu-id="e7bc1-183">**/t\[ype\]:**_typename_</span></span>|<span data-ttu-id="e7bc1-184">指定要为其创建架构的类型的名称。</span><span class="sxs-lookup"><span data-stu-id="e7bc1-184">Specifies the name of the type to create a schema for.</span></span> <span data-ttu-id="e7bc1-185">可以指定多个类型参数。</span><span class="sxs-lookup"><span data-stu-id="e7bc1-185">You can specify multiple type arguments.</span></span> <span data-ttu-id="e7bc1-186">如果 typename 不指定一个命名空间，则 Xsd.exe 将程序集中的所有类型与指定类型相匹配。</span><span class="sxs-lookup"><span data-stu-id="e7bc1-186">If *typename* does not specify a namespace, Xsd.exe matches all types in the assembly with the specified type.</span></span> <span data-ttu-id="e7bc1-187">如果 typename 指定一个命名空间，则仅匹配那个类型。</span><span class="sxs-lookup"><span data-stu-id="e7bc1-187">If *typename* specifies a namespace, only that type is matched.</span></span> <span data-ttu-id="e7bc1-188">如果 typename 以星号字符 (\*) 结尾，则此工具匹配所有以 \* 前的字符串开头的类型。</span><span class="sxs-lookup"><span data-stu-id="e7bc1-188">If *typename* ends with an asterisk character (\*), the tool matches all types that start with the string preceding the \*.</span></span> <span data-ttu-id="e7bc1-189">如果省略 `/type` 选项，则 Xsd.exe 为程序集中的所有类型生成架构。</span><span class="sxs-lookup"><span data-stu-id="e7bc1-189">If you omit the `/type` option, Xsd.exe generates schemas for all types in the assembly.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e7bc1-190">备注</span><span class="sxs-lookup"><span data-stu-id="e7bc1-190">Remarks</span></span>  
 <span data-ttu-id="e7bc1-191">下表显示了 Xsd.exe 执行的操作。</span><span class="sxs-lookup"><span data-stu-id="e7bc1-191">The following table shows the operations that Xsd.exe performs.</span></span>  

| | |  
|------------|-----------------|  
|<span data-ttu-id="e7bc1-192">XDR 到 XSD</span><span class="sxs-lookup"><span data-stu-id="e7bc1-192">XDR to XSD</span></span>|<span data-ttu-id="e7bc1-193">使用精简 XML 数据架构文件生成 XML 架构。</span><span class="sxs-lookup"><span data-stu-id="e7bc1-193">Generates an XML schema from an XML-Data-Reduced schema file.</span></span> <span data-ttu-id="e7bc1-194">XDR 为早期基于 XML 的架构格式。</span><span class="sxs-lookup"><span data-stu-id="e7bc1-194">XDR is an early XML-based schema format.</span></span>| 
|<span data-ttu-id="e7bc1-195">XML 到 XSD</span><span class="sxs-lookup"><span data-stu-id="e7bc1-195">XML to XSD</span></span>|<span data-ttu-id="e7bc1-196">使用 XML 文件生成 XML 架构。</span><span class="sxs-lookup"><span data-stu-id="e7bc1-196">Generates an XML schema from an XML file.</span></span>|  
|<span data-ttu-id="e7bc1-197">XSD 到 DataSet</span><span class="sxs-lookup"><span data-stu-id="e7bc1-197">XSD to DataSet</span></span>|<span data-ttu-id="e7bc1-198">使用 XSD 架构文件生成公共语言运行时 <xref:System.Data.DataSet> 类。</span><span class="sxs-lookup"><span data-stu-id="e7bc1-198">Generates common language runtime <xref:System.Data.DataSet> classes from an XSD schema file.</span></span> <span data-ttu-id="e7bc1-199">生成的类为规则 XML 数据提供复杂对象模型。</span><span class="sxs-lookup"><span data-stu-id="e7bc1-199">The generated classes provide a rich object model for regular XML data.</span></span>| 
|<span data-ttu-id="e7bc1-200">XSD 到类</span><span class="sxs-lookup"><span data-stu-id="e7bc1-200">XSD to Classes</span></span>|<span data-ttu-id="e7bc1-201">使用 XSD 架构文件生成运行时类。</span><span class="sxs-lookup"><span data-stu-id="e7bc1-201">Generates runtime classes from an XSD schema file.</span></span> <span data-ttu-id="e7bc1-202">生成的类可以与 <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> 一起使用，来读写遵循该架构的 XML 代码。</span><span class="sxs-lookup"><span data-stu-id="e7bc1-202">The generated classes can be used in conjunction with <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> to read and write XML code that follows the schema.</span></span>| 
|<span data-ttu-id="e7bc1-203">类到 XSD</span><span class="sxs-lookup"><span data-stu-id="e7bc1-203">Classes to XSD</span></span>| <span data-ttu-id="e7bc1-204">使用运行时程序集文件中的一个或多个类型生成 XML 架构。</span><span class="sxs-lookup"><span data-stu-id="e7bc1-204">Generates an XML schema from a type or types in a runtime assembly file.</span></span> <span data-ttu-id="e7bc1-205">生成的架构定义使用的 XML 格式<xref:System.Xml.Serialization.XmlSerializer>。</span><span class="sxs-lookup"><span data-stu-id="e7bc1-205">The generated schema defines the XML format used by the <xref:System.Xml.Serialization.XmlSerializer>.</span></span>|  
 
 <span data-ttu-id="e7bc1-206">Xsd.exe 只允许操作遵循由万维网联合会 (W3C) 提议的 XML 架构定义 (XSD) 语言的 XML 架构。</span><span class="sxs-lookup"><span data-stu-id="e7bc1-206">Xsd.exe only allows you to manipulate XML schemas that follow the XML Schema Definition (XSD) language proposed by the World Wide Web Consortium (W3C).</span></span> <span data-ttu-id="e7bc1-207">有关 XML 架构定义提议或 XML 标准的详细信息，请参阅<https://w3.org>。</span><span class="sxs-lookup"><span data-stu-id="e7bc1-207">For more information on the XML Schema Definition proposal or the XML standard, see <https://w3.org>.</span></span>  
  
## <a name="setting-options-with-an-xml-file"></a><span data-ttu-id="e7bc1-208">通过 XML 文件设置选项</span><span class="sxs-lookup"><span data-stu-id="e7bc1-208">Setting Options with an XML File</span></span>  
 <span data-ttu-id="e7bc1-209">通过使用 `/parameters` 开关，可指定设置各种选项的单个 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="e7bc1-209">By using the `/parameters` switch, you can specify a single XML file that sets various options.</span></span> <span data-ttu-id="e7bc1-210">可设置的选项取决于您如何使用 XSD.exe 工具。</span><span class="sxs-lookup"><span data-stu-id="e7bc1-210">The options you can set depend on how you are using the XSD.exe tool.</span></span> <span data-ttu-id="e7bc1-211">选择包括生成架构、生成代码文件，或生成包含 `DataSet` 功能的代码文件。</span><span class="sxs-lookup"><span data-stu-id="e7bc1-211">Choices include generating schemas, generating code files, or generating code files that include `DataSet` features.</span></span> <span data-ttu-id="e7bc1-212">例如，生成架构时可将 `<assembly>` 元素设置为可执行文件 (.exe) 或类库文件 (.dll) 的名称，但生成代码文件时则不能。</span><span class="sxs-lookup"><span data-stu-id="e7bc1-212">For example, you can set the `<assembly>` element to the name of an executable (.exe) or type library (.dll) file when generating a schema, but not when generating a code file.</span></span> <span data-ttu-id="e7bc1-213">下面的 XML 演示如何将 `<generateSchemas>` 元素用于指定的可执行文件：</span><span class="sxs-lookup"><span data-stu-id="e7bc1-213">The following XML shows how to use the `<generateSchemas>` element with a specified executable:</span></span>  
  
```xml  
<!-- This is in a file named GenerateSchemas.xml. -->  
<xsd xmlns='http://microsoft.com/dotnet/tools/xsd/'>  
<generateSchemas>  
   <assembly>ConsoleApplication1.exe</assembly>  
</generateSchemas>  
</xsd>  
```  
  
 <span data-ttu-id="e7bc1-214">如果前面的 XML 包含在名为 GenerateSchemas.xml 的文件中，则通过在命令提示处键入下面的内容并按 Enter 使用 `/parameters` 开关：</span><span class="sxs-lookup"><span data-stu-id="e7bc1-214">If the preceding XML is contained in a file named GenerateSchemas.xml, then use the `/parameters` switch by typing the following at a command prompt and pressing ENTER:</span></span>  
  
```console 
 xsd /p:GenerateSchemas.xml 
```  
  
 <span data-ttu-id="e7bc1-215">另外，如果为程序集中的单个类型生成架构，则可以使用下面的 XML：</span><span class="sxs-lookup"><span data-stu-id="e7bc1-215">On the other hand, if you are generating a schema for a single type found in the assembly, you can use the following XML:</span></span>  
  
```xml  
<!-- This is in a file named GenerateSchemaFromType.xml. -->  
<xsd xmlns='http://microsoft.com/dotnet/tools/xsd/'>  
<generateSchemas>  
   <type>IDItems</type>  
</generateSchemas>  
</xsd>  
```  
  
 <span data-ttu-id="e7bc1-216">但是若要使用上面的代码，您还必须在命令提示处提供程序集的名称。</span><span class="sxs-lookup"><span data-stu-id="e7bc1-216">But to use preceding code, you must also supply the name of the assembly at the command prompt.</span></span> <span data-ttu-id="e7bc1-217">在命令提示处键入下面的内容（假设 XML 文件名为 GenerateSchemaFromType.xml）：</span><span class="sxs-lookup"><span data-stu-id="e7bc1-217">Type the following at a command prompt (presuming the XML file is named GenerateSchemaFromType.xml):</span></span>  
  
```console 
xsd /p:GenerateSchemaFromType.xml ConsoleApplication1.exe  
```  
 <span data-ttu-id="e7bc1-218">必须为 `\<generateSchemas>` 元素仅指定以下选项中的一个。</span><span class="sxs-lookup"><span data-stu-id="e7bc1-218">You must specify only one of the following options for the `\<generateSchemas>` element.</span></span>  
  
|<span data-ttu-id="e7bc1-219">元素</span><span class="sxs-lookup"><span data-stu-id="e7bc1-219">Element</span></span>|<span data-ttu-id="e7bc1-220">描述</span><span class="sxs-lookup"><span data-stu-id="e7bc1-220">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e7bc1-221">\<assembly></span><span class="sxs-lookup"><span data-stu-id="e7bc1-221">\<assembly></span></span>|<span data-ttu-id="e7bc1-222">指定将从中生成架构的程序集。</span><span class="sxs-lookup"><span data-stu-id="e7bc1-222">Specifies an assembly to generate the schema from.</span></span>|  
|<span data-ttu-id="e7bc1-223">\<type></span><span class="sxs-lookup"><span data-stu-id="e7bc1-223">\<type></span></span>|<span data-ttu-id="e7bc1-224">指定程序集中找到的要为其生成架构的类型。</span><span class="sxs-lookup"><span data-stu-id="e7bc1-224">Specifies a type found in an assembly to generate a schema for.</span></span>|  
|<span data-ttu-id="e7bc1-225">\<xml></span><span class="sxs-lookup"><span data-stu-id="e7bc1-225">\<xml></span></span>|<span data-ttu-id="e7bc1-226">指定要为其生成架构的 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="e7bc1-226">Specifies an XML file to generate a schema for.</span></span>|  
|<span data-ttu-id="e7bc1-227">\<xdr></span><span class="sxs-lookup"><span data-stu-id="e7bc1-227">\<xdr></span></span>|<span data-ttu-id="e7bc1-228">指定要为其生成架构的 XDR 文件。</span><span class="sxs-lookup"><span data-stu-id="e7bc1-228">Specifies an XDR file to generate a schema for.</span></span>|  
  
 <span data-ttu-id="e7bc1-229">若要生成代码文件，请使用 `<generateClasses>` 元素。</span><span class="sxs-lookup"><span data-stu-id="e7bc1-229">To generate a code file, use the `<generateClasses>` element.</span></span> <span data-ttu-id="e7bc1-230">下面的示例生成一个代码文件。</span><span class="sxs-lookup"><span data-stu-id="e7bc1-230">The following example generates a code file.</span></span> <span data-ttu-id="e7bc1-231">请注意，另外还显示了两个特性，它们允许您为生成的文件设置编程语言和命名空间。</span><span class="sxs-lookup"><span data-stu-id="e7bc1-231">Note that two attributes are also shown that allow you to set the programming language and namespace of the generated file.</span></span>  
  
```xml  
<xsd xmlns='http://microsoft.com/dotnet/tools/xsd/'>  
<generateClasses language='VB' namespace='Microsoft.Serialization.Examples'/>  
</xsd>  
<!-- You must supply an .xsd file when typing in the command line.-->  
<!-- For example: xsd /p:genClasses mySchema.xsd -->  
```  
  
 <span data-ttu-id="e7bc1-232">可为 `\<generateClasses>` 元素设置以下选项。</span><span class="sxs-lookup"><span data-stu-id="e7bc1-232">Options you can set for the `\<generateClasses>` element include the following.</span></span>  
  
|<span data-ttu-id="e7bc1-233">元素</span><span class="sxs-lookup"><span data-stu-id="e7bc1-233">Element</span></span>|<span data-ttu-id="e7bc1-234">描述</span><span class="sxs-lookup"><span data-stu-id="e7bc1-234">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e7bc1-235">\<element></span><span class="sxs-lookup"><span data-stu-id="e7bc1-235">\<element></span></span>|<span data-ttu-id="e7bc1-236">指定 .xsd 文件中要为其生成代码的元素。</span><span class="sxs-lookup"><span data-stu-id="e7bc1-236">Specifies an element in the .xsd file to generate code for.</span></span>|  
|<span data-ttu-id="e7bc1-237">\<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="e7bc1-237">\<schemaImporterExtensions></span></span>|<span data-ttu-id="e7bc1-238">指定派生自 <xref:System.Xml.Serialization.Advanced.SchemaImporterExtension> 类的类型。</span><span class="sxs-lookup"><span data-stu-id="e7bc1-238">Specifies a type derived from the <xref:System.Xml.Serialization.Advanced.SchemaImporterExtension> class.</span></span>|  
|<span data-ttu-id="e7bc1-239">\<schema></span><span class="sxs-lookup"><span data-stu-id="e7bc1-239">\<schema></span></span>|<span data-ttu-id="e7bc1-240">指定要为其生成代码的 XML 架构文件。</span><span class="sxs-lookup"><span data-stu-id="e7bc1-240">Specifies a XML Schema file to generate code for.</span></span>  <span data-ttu-id="e7bc1-241">可使用多个 \<schema> 元素指定多个 XML 架构文件。</span><span class="sxs-lookup"><span data-stu-id="e7bc1-241">Multiple XML Schema files can be specified using multiple \<schema> elements.</span></span>|  
  
 <span data-ttu-id="e7bc1-242">下表显示也可用于 `<generateClasses>` 元素的特性。</span><span class="sxs-lookup"><span data-stu-id="e7bc1-242">The following table shows the attributes that can also be used with the `<generateClasses>` element.</span></span>  
  
|<span data-ttu-id="e7bc1-243">特性</span><span class="sxs-lookup"><span data-stu-id="e7bc1-243">Attribute</span></span>|<span data-ttu-id="e7bc1-244">描述</span><span class="sxs-lookup"><span data-stu-id="e7bc1-244">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e7bc1-245">语言</span><span class="sxs-lookup"><span data-stu-id="e7bc1-245">language</span></span>|<span data-ttu-id="e7bc1-246">指定要使用的编程语言。</span><span class="sxs-lookup"><span data-stu-id="e7bc1-246">Specifies the programming language to use.</span></span> <span data-ttu-id="e7bc1-247">从 `CS`（默认情况下为 C#）、`VB` (Visual Basic)、`JS` (JScript) 或 `VJS` (Visual J#) 中进行选择。</span><span class="sxs-lookup"><span data-stu-id="e7bc1-247">Choose from `CS` (C#, the default), `VB` (Visual Basic), `JS` (JScript), or `VJS` (Visual J#).</span></span> <span data-ttu-id="e7bc1-248">也可指定实现 <xref:System.CodeDom.Compiler.CodeDomProvider> 的类的完全限定名。</span><span class="sxs-lookup"><span data-stu-id="e7bc1-248">You can also specify a fully qualified name for a class that implements <xref:System.CodeDom.Compiler.CodeDomProvider>.</span></span>|  
|<span data-ttu-id="e7bc1-249">namespace</span><span class="sxs-lookup"><span data-stu-id="e7bc1-249">namespace</span></span>|<span data-ttu-id="e7bc1-250">为生成的代码指定命名空间。</span><span class="sxs-lookup"><span data-stu-id="e7bc1-250">Specifies the namespace for the generated code.</span></span> <span data-ttu-id="e7bc1-251">命名空间必须符合 CLR 标准（例如，没有空格或反斜杠字符）。</span><span class="sxs-lookup"><span data-stu-id="e7bc1-251">The namespace must conform to CLR standards (for example, no spaces or backslash characters).</span></span>|  
|<span data-ttu-id="e7bc1-252">选项</span><span class="sxs-lookup"><span data-stu-id="e7bc1-252">options</span></span>|<span data-ttu-id="e7bc1-253">以下值之一：`none`、`properties`（生成属性而不是公共字段）、`order` 或 `enableDataBinding`（请参见前面“XSD 文件选项”一节的 `/order` 和 `/enableDataBinding` 开关）。</span><span class="sxs-lookup"><span data-stu-id="e7bc1-253">One of the following values: `none`, `properties` (generates properties instead of public fields), `order`, or `enableDataBinding` (see the `/order` and `/enableDataBinding` switches in the preceding XSD File Options section.</span></span>|  
  
 <span data-ttu-id="e7bc1-254">使用 `DataSet` 元素还可以控制如何生成 `<generateDataSet>` 代码。</span><span class="sxs-lookup"><span data-stu-id="e7bc1-254">You can also control how `DataSet` code is generated by using the `<generateDataSet>` element.</span></span> <span data-ttu-id="e7bc1-255">下面的 XML 指定生成的代码使用 `DataSet` 结构（如 <xref:System.Data.DataTable> 类）为指定元素创建 Visual Basic 代码。</span><span class="sxs-lookup"><span data-stu-id="e7bc1-255">The following XML specifies that the generated codeuses `DataSet` structures (such as the <xref:System.Data.DataTable> class) to create Visual Basic code for a specified element.</span></span> <span data-ttu-id="e7bc1-256">生成的数据集结构将支持 LINQ 查询。</span><span class="sxs-lookup"><span data-stu-id="e7bc1-256">The generated DataSet structures will support LINQ queries.</span></span>  
  
 ```xml 
 <xsd xmlns='http://microsoft.com/dotnet/tools/xsd/'> 
     <generateDataSet language='VB' namespace='Microsoft.Serialization.Examples' enableLinqDataSet='true'> 
     </generateDataSet>    
 </xsd> 
``` 
 
 <span data-ttu-id="e7bc1-257">可为 `<generateDataSet>` 元素设置以下选项。</span><span class="sxs-lookup"><span data-stu-id="e7bc1-257">Options you can set for the `<generateDataSet>` element include the following.</span></span>  
  
|<span data-ttu-id="e7bc1-258">元素</span><span class="sxs-lookup"><span data-stu-id="e7bc1-258">Element</span></span>|<span data-ttu-id="e7bc1-259">描述</span><span class="sxs-lookup"><span data-stu-id="e7bc1-259">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e7bc1-260">\<schema></span><span class="sxs-lookup"><span data-stu-id="e7bc1-260">\<schema></span></span>|<span data-ttu-id="e7bc1-261">指定要为其生成代码的 XML 架构文件。</span><span class="sxs-lookup"><span data-stu-id="e7bc1-261">Specifies an XML Schema file to generate code for.</span></span> <span data-ttu-id="e7bc1-262">可使用多个 \<schema> 元素指定多个 XML 架构文件。</span><span class="sxs-lookup"><span data-stu-id="e7bc1-262">Multiple XML Schema files can be specified using multiple \<schema> elements.</span></span>|  
  
 <span data-ttu-id="e7bc1-263">下表显示可与 `<generateDataSet>` 元素一起使用的特性。</span><span class="sxs-lookup"><span data-stu-id="e7bc1-263">The following table shows the attributes that can be used with the `<generateDataSet>` element.</span></span>  
  
|<span data-ttu-id="e7bc1-264">特性</span><span class="sxs-lookup"><span data-stu-id="e7bc1-264">Attribute</span></span>|<span data-ttu-id="e7bc1-265">描述</span><span class="sxs-lookup"><span data-stu-id="e7bc1-265">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e7bc1-266">enableLinqDataSet</span><span class="sxs-lookup"><span data-stu-id="e7bc1-266">enableLinqDataSet</span></span>|<span data-ttu-id="e7bc1-267">指定可使用 LINQ to DataSet 查询的生成的数据集。</span><span class="sxs-lookup"><span data-stu-id="e7bc1-267">Specifies that the generated DataSet can be queried against using LINQ to DataSet.</span></span> <span data-ttu-id="e7bc1-268">默认值为 False。</span><span class="sxs-lookup"><span data-stu-id="e7bc1-268">The default value is false.</span></span>|  
|<span data-ttu-id="e7bc1-269">语言</span><span class="sxs-lookup"><span data-stu-id="e7bc1-269">language</span></span>|<span data-ttu-id="e7bc1-270">指定要使用的编程语言。</span><span class="sxs-lookup"><span data-stu-id="e7bc1-270">Specifies the programming language to use.</span></span> <span data-ttu-id="e7bc1-271">从 `CS`（默认情况下为 C#）、`VB` (Visual Basic)、`JS` (JScript) 或 `VJS` (Visual J#) 中进行选择。</span><span class="sxs-lookup"><span data-stu-id="e7bc1-271">Choose from `CS` (C#, the default), `VB` (Visual Basic), `JS` (JScript), or `VJS` (Visual J#).</span></span> <span data-ttu-id="e7bc1-272">也可指定实现 <xref:System.CodeDom.Compiler.CodeDomProvider> 的类的完全限定名。</span><span class="sxs-lookup"><span data-stu-id="e7bc1-272">You can also specify a fully qualified name for a class that implements <xref:System.CodeDom.Compiler.CodeDomProvider>.</span></span>|  
|<span data-ttu-id="e7bc1-273">namespace</span><span class="sxs-lookup"><span data-stu-id="e7bc1-273">namespace</span></span>|<span data-ttu-id="e7bc1-274">为生成的代码指定命名空间。</span><span class="sxs-lookup"><span data-stu-id="e7bc1-274">Specifies the namespace for the generated code.</span></span> <span data-ttu-id="e7bc1-275">命名空间必须符合 CLR 标准（例如，没有空格或反斜杠字符）。</span><span class="sxs-lookup"><span data-stu-id="e7bc1-275">The namespace must conform to CLR standards (for example, no spaces or backslash characters).</span></span>|  
  
 <span data-ttu-id="e7bc1-276">有些特性可在顶级 `<xsd>` 元素上设置。</span><span class="sxs-lookup"><span data-stu-id="e7bc1-276">There are attributes that you can set on the top level `<xsd>` element.</span></span> <span data-ttu-id="e7bc1-277">这些选项可用于任何子元素（`<generateSchemas>`、`<generateClasses>` 或 `<generateDataSet>`）。</span><span class="sxs-lookup"><span data-stu-id="e7bc1-277">These options can be used with any of the child elements (`<generateSchemas>`, `<generateClasses>` or `<generateDataSet>`).</span></span> <span data-ttu-id="e7bc1-278">下面的 XML 代码在名为“MyOutputDirectory”的输出目录中为名为“IDItems”的元素生成代码。</span><span class="sxs-lookup"><span data-stu-id="e7bc1-278">The following XML code generates code for an element named "IDItems" in the output directory named "MyOutputDirectory".</span></span>  
  
```xml  
<xsd xmlns='http://microsoft.com/dotnet/tools/xsd/' output='MyOutputDirectory'>  
<generateClasses>  
    <element>IDItems</element>  
</generateClasses>  
</xsd>  
```  
  
 <span data-ttu-id="e7bc1-279">下表显示也可用于 `\<xsd>` 元素的特性。</span><span class="sxs-lookup"><span data-stu-id="e7bc1-279">The following table shows the attributes that can also be used with the `\<xsd>` element.</span></span>  
  
|<span data-ttu-id="e7bc1-280">特性</span><span class="sxs-lookup"><span data-stu-id="e7bc1-280">Attribute</span></span>|<span data-ttu-id="e7bc1-281">描述</span><span class="sxs-lookup"><span data-stu-id="e7bc1-281">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e7bc1-282">输出</span><span class="sxs-lookup"><span data-stu-id="e7bc1-282">output</span></span>|<span data-ttu-id="e7bc1-283">将放置生成的架构或代码文件的目录的名称。</span><span class="sxs-lookup"><span data-stu-id="e7bc1-283">The name of a directory where the generated schema or code file will be placed.</span></span>|  
|<span data-ttu-id="e7bc1-284">nologo</span><span class="sxs-lookup"><span data-stu-id="e7bc1-284">nologo</span></span>|<span data-ttu-id="e7bc1-285">取消显示版权标志。</span><span class="sxs-lookup"><span data-stu-id="e7bc1-285">Suppresses the banner.</span></span> <span data-ttu-id="e7bc1-286">设置为 `true` 或 `false`。</span><span class="sxs-lookup"><span data-stu-id="e7bc1-286">Set to `true` or `false`.</span></span>|  
|<span data-ttu-id="e7bc1-287">帮助</span><span class="sxs-lookup"><span data-stu-id="e7bc1-287">help</span></span>|<span data-ttu-id="e7bc1-288">显示该工具的命令语法和选项。</span><span class="sxs-lookup"><span data-stu-id="e7bc1-288">Displays command syntax and options for the tool.</span></span> <span data-ttu-id="e7bc1-289">设置为 `true` 或 `false`。</span><span class="sxs-lookup"><span data-stu-id="e7bc1-289">Set to `true` or `false`.</span></span>|  
  
## <a name="examples"></a><span data-ttu-id="e7bc1-290">示例</span><span class="sxs-lookup"><span data-stu-id="e7bc1-290">Examples</span></span>  
 <span data-ttu-id="e7bc1-291">下面的命令从 `myFile.xdr` 生成一个 XML 架构并将它保存到当前目录中。</span><span class="sxs-lookup"><span data-stu-id="e7bc1-291">The following command generates an XML schema from `myFile.xdr` and saves it to the current directory.</span></span>  
  
```console  
xsd myFile.xdr   
```  
  
 <span data-ttu-id="e7bc1-292">下面的命令从 `myFile.xml` 生成一个 XML 架构并将它保存到指定目录中。</span><span class="sxs-lookup"><span data-stu-id="e7bc1-292">The following command generates an XML schema from `myFile.xml` and saves it to the specified directory.</span></span>  
  
```console  
xsd myFile.xml /outputdir:myOutputDir  
```  
  
 <span data-ttu-id="e7bc1-293">下面的命令生成一个与 C# 语言中的指定架构相对应的数据集，并在当前目录中将其保存为 `XSDSchemaFile.cs`。</span><span class="sxs-lookup"><span data-stu-id="e7bc1-293">The following command generates a data set that corresponds to the specified schema in the C# language and saves it as `XSDSchemaFile.cs` in the current directory.</span></span>  
  
```console  
xsd /dataset /language:CS XSDSchemaFile.xsd  
```  
  
 <span data-ttu-id="e7bc1-294">下面的命令为程序集 `myAssembly.dll` 中的所有类型生成 XML 架构，并在当前目录中将它们保存为 `schema0.xsd`。</span><span class="sxs-lookup"><span data-stu-id="e7bc1-294">The following command generates XML schemas for all types in the assembly `myAssembly.dll` and saves them as `schema0.xsd` in the current directory.</span></span>  
  
```console  
xsd myAssembly.dll    
```  
  
## <a name="see-also"></a><span data-ttu-id="e7bc1-295">请参阅</span><span class="sxs-lookup"><span data-stu-id="e7bc1-295">See also</span></span>

- <xref:System.Data.DataSet>  
- <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType>  
- [<span data-ttu-id="e7bc1-296">工具</span><span class="sxs-lookup"><span data-stu-id="e7bc1-296">Tools</span></span>](../../../docs/framework/tools/index.md)      
- [<span data-ttu-id="e7bc1-297">命令提示</span><span class="sxs-lookup"><span data-stu-id="e7bc1-297">Command Prompts</span></span>](../../../docs/framework/tools/developer-command-prompt-for-vs.md)  
- [<span data-ttu-id="e7bc1-298">LINQ to DataSet 概述</span><span class="sxs-lookup"><span data-stu-id="e7bc1-298">LINQ to DataSet Overview</span></span>](../../../docs/framework/data/adonet/linq-to-dataset-overview.md)  
- [<span data-ttu-id="e7bc1-299">查询类型化数据集</span><span class="sxs-lookup"><span data-stu-id="e7bc1-299">Querying Typed DataSets</span></span>](../../../docs/framework/data/adonet/querying-typed-datasets.md)  
- [<span data-ttu-id="e7bc1-300">LINQ（语言集成查询）</span><span class="sxs-lookup"><span data-stu-id="e7bc1-300">LINQ (Language-Integrated Query)</span></span>](https://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d)
