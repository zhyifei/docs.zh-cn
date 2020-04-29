---
title: XML Schema Definition Tool (Xsd.exe)
ms.date: 03/30/2017
ms.assetid: a6e6e65c-347f-4494-9457-653bf29baac2
ms.openlocfilehash: 6ec99e77db4215184547ea2bbbe0d1ff8ad3c286
ms.sourcegitcommit: c91110ef6ee3fedb591f3d628dc17739c4a7071e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/15/2020
ms.locfileid: "81389775"
---
# <a name="xml-schema-definition-tool-xsdexe"></a><span data-ttu-id="0c4ba-102">XML Schema Definition Tool (Xsd.exe)</span><span class="sxs-lookup"><span data-stu-id="0c4ba-102">XML Schema Definition Tool (Xsd.exe)</span></span>

<span data-ttu-id="0c4ba-103">XML 架构定义 (Xsd.exe) 工具从 XDR、XML 和 XSD 文件或者从运行时程序集中的类生成 XML 架构或公共语言运行时类。</span><span class="sxs-lookup"><span data-stu-id="0c4ba-103">The XML Schema Definition (Xsd.exe) tool generates XML schema or common language runtime classes from XDR, XML, and XSD files, or from classes in a runtime assembly.</span></span>

<span data-ttu-id="0c4ba-104">XML 架构定义工具 (Xsd.exe) 通常可在以下路径中找到：</span><span class="sxs-lookup"><span data-stu-id="0c4ba-104">The XML Schema Definition tool (Xsd.exe) usually can be found in the following path:</span></span>\
<span data-ttu-id="0c4ba-105">C:\\Program Files (x86)\\Microsoft SDKs\\Windows\\{版本}\\bin\\NETFX {版本} Tools\\ </span><span class="sxs-lookup"><span data-stu-id="0c4ba-105">_C:\\Program Files (x86)\\Microsoft SDKs\\Windows\\{version}\\bin\\NETFX {version} Tools\\_</span></span>

## <a name="syntax"></a><span data-ttu-id="0c4ba-106">语法</span><span class="sxs-lookup"><span data-stu-id="0c4ba-106">Syntax</span></span>

<span data-ttu-id="0c4ba-107">从命令行运行该工具。</span><span class="sxs-lookup"><span data-stu-id="0c4ba-107">Run the tool from the command line.</span></span>

```console
xsd file.xdr [-outputdir:directory][/parameters:file.xml]
xsd file.xml [-outputdir:directory] [/parameters:file.xml]
xsd file.xsd {/classes | /dataset} [/element:element]
             [/enableLinqDataSet] [/language:language]
                          [/namespace:namespace] [-outputdir:directory] [URI:uri]
                          [/parameters:file.xml]
xsd {file.dll | file.exe} [-outputdir:directory] [/type:typename [...]][/parameters:file.xml]
```
  
> [!TIP]
> <span data-ttu-id="0c4ba-108">要使 .NET Framework 工具正常发挥作用，必须正确设置 `Path`、`Include` 和 `Lib` 环境变量。</span><span class="sxs-lookup"><span data-stu-id="0c4ba-108">For .NET Framework tools to function properly, you must set your `Path`, `Include`, and `Lib` environment variables correctly.</span></span> <span data-ttu-id="0c4ba-109">可以通过运行 SDKVars.bat（位于 \<SDK>\v2.0\Bin 目录中）来设置这些环境变量。</span><span class="sxs-lookup"><span data-stu-id="0c4ba-109">Set these environment variables by running SDKVars.bat, which is located in the \<SDK>\v2.0\Bin directory.</span></span> <span data-ttu-id="0c4ba-110">必须在每个命令 shell 程序中执行 SDKVars.bat。</span><span class="sxs-lookup"><span data-stu-id="0c4ba-110">SDKVars.bat must be executed in every command shell.</span></span>

## <a name="argument"></a><span data-ttu-id="0c4ba-111">参数</span><span class="sxs-lookup"><span data-stu-id="0c4ba-111">Argument</span></span>

|<span data-ttu-id="0c4ba-112">参数</span><span class="sxs-lookup"><span data-stu-id="0c4ba-112">Argument</span></span>|<span data-ttu-id="0c4ba-113">描述</span><span class="sxs-lookup"><span data-stu-id="0c4ba-113">Description</span></span>|
|--------------|-----------------|
|<span data-ttu-id="0c4ba-114">file.extension </span><span class="sxs-lookup"><span data-stu-id="0c4ba-114">*file.extension*</span></span>|<span data-ttu-id="0c4ba-115">指定要转换的输入文件。</span><span class="sxs-lookup"><span data-stu-id="0c4ba-115">Specifies the input file to convert.</span></span> <span data-ttu-id="0c4ba-116">必须将扩展名指定为下列之一：.xdr、.xml、.xsd、.dll 或 .exe。</span><span class="sxs-lookup"><span data-stu-id="0c4ba-116">You must specify the extension as one of the following: .xdr, .xml, .xsd, .dll, or .exe.</span></span><br /><br /> <span data-ttu-id="0c4ba-117">如果指定一个 XDR 架构文件（.xdr 扩展名），则 Xsd.exe 将 XDR 架构转换为 XSD 架构。</span><span class="sxs-lookup"><span data-stu-id="0c4ba-117">If you specify an XDR schema file (.xdr extension), Xsd.exe converts the XDR schema to an XSD schema.</span></span> <span data-ttu-id="0c4ba-118">输出文件与 XDR 架构同名，但扩展名为 .xsd。</span><span class="sxs-lookup"><span data-stu-id="0c4ba-118">The output file has the same name as the XDR schema, but with the .xsd extension.</span></span><br /><br /> <span data-ttu-id="0c4ba-119">如果指定一个 XML 文件（.xml 扩展名），则 Xsd.exe 从文件中的数据推导出架构并产生一个 XSD 架构。</span><span class="sxs-lookup"><span data-stu-id="0c4ba-119">If you specify an XML file (.xml extension), Xsd.exe infers a schema from the data in the file and produces an XSD schema.</span></span> <span data-ttu-id="0c4ba-120">输出文件与 XML 文件同名，但扩展名为 .xsd。</span><span class="sxs-lookup"><span data-stu-id="0c4ba-120">The output file has the same name as the XML file, but with the .xsd extension.</span></span><br /><br /> <span data-ttu-id="0c4ba-121">如果指定一个 XML 架构文件（.xsd 扩展名），则 Xsd.exe 将为对应于 XML 架构的运行时对象生成源代码。</span><span class="sxs-lookup"><span data-stu-id="0c4ba-121">If you specify an XML schema file (.xsd extension), Xsd.exe generates source code for runtime objects that correspond to the XML schema.</span></span><br /><br /> <span data-ttu-id="0c4ba-122">如果指定一个运行时程序集文件（.exe 或 .dll 扩展名），则 Xsd.exe 为该程序集中的一个或多个类型生成架构。</span><span class="sxs-lookup"><span data-stu-id="0c4ba-122">If you specify a runtime assembly file (.exe or .dll extension), Xsd.exe generates schemas for one or more types in that assembly.</span></span> <span data-ttu-id="0c4ba-123">可以使用 `/type` 选项来指定为其生成架构的类型。</span><span class="sxs-lookup"><span data-stu-id="0c4ba-123">You can use the `/type` option to specify the types for which to generate schemas.</span></span> <span data-ttu-id="0c4ba-124">输出架构被命名为 schema0.xsd、schema1.xsd，依此类推。</span><span class="sxs-lookup"><span data-stu-id="0c4ba-124">The output schemas are named schema0.xsd, schema1.xsd, and so on.</span></span> <span data-ttu-id="0c4ba-125">仅当给定类型使用 `XMLRoot` 自定义特性指定命名空间时，Xsd.exe 才生成多个架构。</span><span class="sxs-lookup"><span data-stu-id="0c4ba-125">Xsd.exe produces multiple schemas only if the given types specify a namespace using the `XMLRoot` custom attribute.</span></span>|

## <a name="general-options"></a><span data-ttu-id="0c4ba-126">常规选项</span><span class="sxs-lookup"><span data-stu-id="0c4ba-126">General Options</span></span>

|<span data-ttu-id="0c4ba-127">选项</span><span class="sxs-lookup"><span data-stu-id="0c4ba-127">Option</span></span>|<span data-ttu-id="0c4ba-128">描述</span><span class="sxs-lookup"><span data-stu-id="0c4ba-128">Description</span></span>|
|------------|-----------------|
|<span data-ttu-id="0c4ba-129">/h\[elp\] </span><span class="sxs-lookup"><span data-stu-id="0c4ba-129">**/h\[elp\]**</span></span>|<span data-ttu-id="0c4ba-130">显示该工具的命令语法和选项。</span><span class="sxs-lookup"><span data-stu-id="0c4ba-130">Displays command syntax and options for the tool.</span></span>|
|<span data-ttu-id="0c4ba-131">/o\[utputdir\]:directory  </span><span class="sxs-lookup"><span data-stu-id="0c4ba-131">**/o\[utputdir\]:**_directory_</span></span>|<span data-ttu-id="0c4ba-132">指定输出文件的目录。</span><span class="sxs-lookup"><span data-stu-id="0c4ba-132">Specifies the directory for output files.</span></span> <span data-ttu-id="0c4ba-133">此参数只能出现一次。</span><span class="sxs-lookup"><span data-stu-id="0c4ba-133">This argument can appear only once.</span></span> <span data-ttu-id="0c4ba-134">默认为当前目录。</span><span class="sxs-lookup"><span data-stu-id="0c4ba-134">The default is the current directory.</span></span>|
|<span data-ttu-id="0c4ba-135">**/?**</span><span class="sxs-lookup"><span data-stu-id="0c4ba-135">**/?**</span></span>|<span data-ttu-id="0c4ba-136">显示该工具的命令语法和选项。</span><span class="sxs-lookup"><span data-stu-id="0c4ba-136">Displays command syntax and options for the tool.</span></span>|
|<span data-ttu-id="0c4ba-137">/p\[arameters\]:file.xml  </span><span class="sxs-lookup"><span data-stu-id="0c4ba-137">**/p\[arameters\]:**_file.xml_</span></span>|<span data-ttu-id="0c4ba-138">从指定的 .xml 文件读取各种操作模式的选项。</span><span class="sxs-lookup"><span data-stu-id="0c4ba-138">Read options for various operation modes from the specified .xml file.</span></span> <span data-ttu-id="0c4ba-139">缩写形式为 `/p:`。</span><span class="sxs-lookup"><span data-stu-id="0c4ba-139">The short form is `/p:`.</span></span> <span data-ttu-id="0c4ba-140">有关详细信息，请参阅[备注](#remarks)部分。</span><span class="sxs-lookup"><span data-stu-id="0c4ba-140">For more information, see the [Remarks](#remarks) section.</span></span>|

## <a name="xsd-file-options"></a><span data-ttu-id="0c4ba-141">XSD 文件选项</span><span class="sxs-lookup"><span data-stu-id="0c4ba-141">XSD File Options</span></span>
 <span data-ttu-id="0c4ba-142">必须为 xsd 文件仅指定下列选项中的一个。</span><span class="sxs-lookup"><span data-stu-id="0c4ba-142">You must specify only one of the following options for .xsd files.</span></span>

|<span data-ttu-id="0c4ba-143">选项</span><span class="sxs-lookup"><span data-stu-id="0c4ba-143">Option</span></span>|<span data-ttu-id="0c4ba-144">描述</span><span class="sxs-lookup"><span data-stu-id="0c4ba-144">Description</span></span>|
|------------|-----------------|
|<span data-ttu-id="0c4ba-145">/c\[lasses\] </span><span class="sxs-lookup"><span data-stu-id="0c4ba-145">**/c\[lasses\]**</span></span>|<span data-ttu-id="0c4ba-146">生成与指定架构相对应的类。</span><span class="sxs-lookup"><span data-stu-id="0c4ba-146">Generates classes that correspond to the specified schema.</span></span> <span data-ttu-id="0c4ba-147">若要将 XML 数据读入对象中，请使用 <xref:System.Xml.Serialization.XmlSerializer.Deserialize%2A?displayProperty=nameWithType> 方法。</span><span class="sxs-lookup"><span data-stu-id="0c4ba-147">To read XML data into the object, use the <xref:System.Xml.Serialization.XmlSerializer.Deserialize%2A?displayProperty=nameWithType> method.</span></span>|
|<span data-ttu-id="0c4ba-148">/d\[ataset\] </span><span class="sxs-lookup"><span data-stu-id="0c4ba-148">**/d\[ataset\]**</span></span>|<span data-ttu-id="0c4ba-149">生成一个从 <xref:System.Data.DataSet> 派生的类，该类与指定的架构相对应。</span><span class="sxs-lookup"><span data-stu-id="0c4ba-149">Generates a class derived from <xref:System.Data.DataSet> that corresponds to the specified schema.</span></span> <span data-ttu-id="0c4ba-150">若要将 XML 数据读入派生类中，请使用 <xref:System.Data.DataSet.ReadXml%2A?displayProperty=nameWithType> 方法。</span><span class="sxs-lookup"><span data-stu-id="0c4ba-150">To read XML data into the derived class, use the <xref:System.Data.DataSet.ReadXml%2A?displayProperty=nameWithType> method.</span></span>|

 <span data-ttu-id="0c4ba-151">还可以为 .xsd 文件指定下列任何选项。</span><span class="sxs-lookup"><span data-stu-id="0c4ba-151">You can also specify any of the following options for .xsd files.</span></span>

|<span data-ttu-id="0c4ba-152">选项</span><span class="sxs-lookup"><span data-stu-id="0c4ba-152">Option</span></span>|<span data-ttu-id="0c4ba-153">描述</span><span class="sxs-lookup"><span data-stu-id="0c4ba-153">Description</span></span>|
|------------|-----------------|
|<span data-ttu-id="0c4ba-154">/e\[lement\]:element  </span><span class="sxs-lookup"><span data-stu-id="0c4ba-154">**/e\[lement\]:**_element_</span></span>|<span data-ttu-id="0c4ba-155">指定架构中要为其生成代码的元素。</span><span class="sxs-lookup"><span data-stu-id="0c4ba-155">Specifies the element in the schema to generate code for.</span></span> <span data-ttu-id="0c4ba-156">默认情况下，键入所有元素。</span><span class="sxs-lookup"><span data-stu-id="0c4ba-156">By default all elements are typed.</span></span> <span data-ttu-id="0c4ba-157">可以多次指定该参数。</span><span class="sxs-lookup"><span data-stu-id="0c4ba-157">You can specify this argument more than once.</span></span>|
|<span data-ttu-id="0c4ba-158">**/enableDataBinding**</span><span class="sxs-lookup"><span data-stu-id="0c4ba-158">**/enableDataBinding**</span></span>|<span data-ttu-id="0c4ba-159">在所有生成的类型上实现 <xref:System.ComponentModel.INotifyPropertyChanged> 接口以启用数据绑定。</span><span class="sxs-lookup"><span data-stu-id="0c4ba-159">Implements the <xref:System.ComponentModel.INotifyPropertyChanged> interface on all generated types to enable data binding.</span></span> <span data-ttu-id="0c4ba-160">缩写形式为 `/edb`。</span><span class="sxs-lookup"><span data-stu-id="0c4ba-160">The short form is `/edb`.</span></span>|
|<span data-ttu-id="0c4ba-161">**/enableLinqDataSet**</span><span class="sxs-lookup"><span data-stu-id="0c4ba-161">**/enableLinqDataSet**</span></span>|<span data-ttu-id="0c4ba-162">（缩写形式：`/eld`。）指定可使用 LINQ to DataSet 查询的生成的数据集。</span><span class="sxs-lookup"><span data-stu-id="0c4ba-162">(Short form: `/eld`.) Specifies that the generated DataSet can be queried against using LINQ to DataSet.</span></span> <span data-ttu-id="0c4ba-163">此选项在同时指定 /dataset 选项的情况下使用。</span><span class="sxs-lookup"><span data-stu-id="0c4ba-163">This option is used when the /dataset option is also specified.</span></span> <span data-ttu-id="0c4ba-164">有关详细信息，请参阅 [LINQ to DataSet 概述](../../../docs/framework/data/adonet/linq-to-dataset-overview.md)和[查询类型化数据集](../../../docs/framework/data/adonet/querying-typed-datasets.md)。</span><span class="sxs-lookup"><span data-stu-id="0c4ba-164">For more information, see [LINQ to DataSet Overview](../../../docs/framework/data/adonet/linq-to-dataset-overview.md) and [Querying Typed DataSets](../../../docs/framework/data/adonet/querying-typed-datasets.md).</span></span> <span data-ttu-id="0c4ba-165">有关使用 LINQ 的常规信息，请参阅[语言集成查询 (LINQ) - C#](../../csharp/programming-guide/concepts/linq/index.md) 或[语言集成查询 (LINQ) - Visual Basic](../../visual-basic/programming-guide/concepts/linq/index.md)。</span><span class="sxs-lookup"><span data-stu-id="0c4ba-165">For general information about using LINQ, see [Language-Integrated Query (LINQ) - C#](../../csharp/programming-guide/concepts/linq/index.md) or [Language-Integrated Query (LINQ) - Visual Basic](../../visual-basic/programming-guide/concepts/linq/index.md).</span></span>|
|<span data-ttu-id="0c4ba-166">/f\[ields\] </span><span class="sxs-lookup"><span data-stu-id="0c4ba-166">**/f\[ields\]**</span></span>|<span data-ttu-id="0c4ba-167">生成字段，而不是生成属性。</span><span class="sxs-lookup"><span data-stu-id="0c4ba-167">Generates fields instead of properties.</span></span> <span data-ttu-id="0c4ba-168">默认情况下生成属性。</span><span class="sxs-lookup"><span data-stu-id="0c4ba-168">By default, properties are generated.</span></span>|
|<span data-ttu-id="0c4ba-169">/l\[anguage\]:language  </span><span class="sxs-lookup"><span data-stu-id="0c4ba-169">**/l\[anguage\]:**_language_</span></span>|<span data-ttu-id="0c4ba-170">指定要使用的编程语言。</span><span class="sxs-lookup"><span data-stu-id="0c4ba-170">Specifies the programming language to use.</span></span> <span data-ttu-id="0c4ba-171">从 `CS`（默认情况下为 C#）、`VB` (Visual Basic)、`JS` (JScript) 或 `VJS` (Visual J#) 中进行选择。</span><span class="sxs-lookup"><span data-stu-id="0c4ba-171">Choose from `CS` (C#, which is the default), `VB` (Visual Basic), `JS` (JScript), or `VJS` (Visual J#).</span></span> <span data-ttu-id="0c4ba-172">也可指定实现 <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType> 的类的完全限定名</span><span class="sxs-lookup"><span data-stu-id="0c4ba-172">You can also specify a fully qualified name for a class implementing <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType></span></span>|
|<span data-ttu-id="0c4ba-173">/n\[amespace\]:namespace  </span><span class="sxs-lookup"><span data-stu-id="0c4ba-173">**/n\[amespace\]:**_namespace_</span></span>|<span data-ttu-id="0c4ba-174">为生成的类型指定运行时命名空间。</span><span class="sxs-lookup"><span data-stu-id="0c4ba-174">Specifies the runtime namespace for the generated types.</span></span> <span data-ttu-id="0c4ba-175">默认命名空间为 `Schemas`。</span><span class="sxs-lookup"><span data-stu-id="0c4ba-175">The default namespace is `Schemas`.</span></span>|
|<span data-ttu-id="0c4ba-176">**/nologo**</span><span class="sxs-lookup"><span data-stu-id="0c4ba-176">**/nologo**</span></span>|<span data-ttu-id="0c4ba-177">取消显示版权标志。</span><span class="sxs-lookup"><span data-stu-id="0c4ba-177">Suppresses the banner.</span></span>|
|<span data-ttu-id="0c4ba-178">**/order**</span><span class="sxs-lookup"><span data-stu-id="0c4ba-178">**/order**</span></span>|<span data-ttu-id="0c4ba-179">在所有粒子成员上生成显式顺序标识符。</span><span class="sxs-lookup"><span data-stu-id="0c4ba-179">Generates explicit order identifiers on all particle members.</span></span>|
|<span data-ttu-id="0c4ba-180">/o\[ut\]:directoryName  </span><span class="sxs-lookup"><span data-stu-id="0c4ba-180">**/o\[ut\]:**_directoryName_</span></span>|<span data-ttu-id="0c4ba-181">指定用来放置文件的输出目录。</span><span class="sxs-lookup"><span data-stu-id="0c4ba-181">Specifies the output directory to place the files in.</span></span> <span data-ttu-id="0c4ba-182">默认为当前目录。</span><span class="sxs-lookup"><span data-stu-id="0c4ba-182">The default is the current directory.</span></span>|
|<span data-ttu-id="0c4ba-183">/u\[ri\]:uri  </span><span class="sxs-lookup"><span data-stu-id="0c4ba-183">**/u\[ri\]:**_uri_</span></span>|<span data-ttu-id="0c4ba-184">为架构中要为其生成代码的元素指定 URI。</span><span class="sxs-lookup"><span data-stu-id="0c4ba-184">Specifies the URI for the elements in the schema to generate code for.</span></span> <span data-ttu-id="0c4ba-185">该 URI（如果存在）应用于使用 `/element` 选项指定的所有元素。</span><span class="sxs-lookup"><span data-stu-id="0c4ba-185">This URI, if present, applies to all elements specified with the `/element` option.</span></span>|

## <a name="dll-and-exe-file-options"></a><span data-ttu-id="0c4ba-186">DLL 和 EXE 文件选项</span><span class="sxs-lookup"><span data-stu-id="0c4ba-186">DLL and EXE File Options</span></span>

|<span data-ttu-id="0c4ba-187">选项</span><span class="sxs-lookup"><span data-stu-id="0c4ba-187">Option</span></span>|<span data-ttu-id="0c4ba-188">描述</span><span class="sxs-lookup"><span data-stu-id="0c4ba-188">Description</span></span>|
|------------|-----------------|
|<span data-ttu-id="0c4ba-189">/t\[ype\]:typename  </span><span class="sxs-lookup"><span data-stu-id="0c4ba-189">**/t\[ype\]:**_typename_</span></span>|<span data-ttu-id="0c4ba-190">指定要为其创建架构的类型的名称。</span><span class="sxs-lookup"><span data-stu-id="0c4ba-190">Specifies the name of the type to create a schema for.</span></span> <span data-ttu-id="0c4ba-191">可以指定多个类型参数。</span><span class="sxs-lookup"><span data-stu-id="0c4ba-191">You can specify multiple type arguments.</span></span> <span data-ttu-id="0c4ba-192">如果 typename 不指定一个命名空间，则 Xsd.exe 将程序集中的所有类型与指定类型相匹配  。</span><span class="sxs-lookup"><span data-stu-id="0c4ba-192">If *typename* does not specify a namespace, Xsd.exe matches all types in the assembly with the specified type.</span></span> <span data-ttu-id="0c4ba-193">如果 typename 指定一个命名空间，则仅匹配那个类型  。</span><span class="sxs-lookup"><span data-stu-id="0c4ba-193">If *typename* specifies a namespace, only that type is matched.</span></span> <span data-ttu-id="0c4ba-194">如果 typename 以星号字符 (\*) 结尾，则此工具匹配所有以 \* 前的字符串开头的类型  。</span><span class="sxs-lookup"><span data-stu-id="0c4ba-194">If *typename* ends with an asterisk character (\*), the tool matches all types that start with the string preceding the \*.</span></span> <span data-ttu-id="0c4ba-195">如果省略 `/type` 选项，则 Xsd.exe 为程序集中的所有类型生成架构。</span><span class="sxs-lookup"><span data-stu-id="0c4ba-195">If you omit the `/type` option, Xsd.exe generates schemas for all types in the assembly.</span></span>|

## <a name="remarks"></a><span data-ttu-id="0c4ba-196">备注</span><span class="sxs-lookup"><span data-stu-id="0c4ba-196">Remarks</span></span>

<span data-ttu-id="0c4ba-197">下表显示了 Xsd.exe 执行的操作。</span><span class="sxs-lookup"><span data-stu-id="0c4ba-197">The following table shows the operations that Xsd.exe performs.</span></span>

| | |
|------------|-----------------|
|<span data-ttu-id="0c4ba-198">XDR 到 XSD</span><span class="sxs-lookup"><span data-stu-id="0c4ba-198">XDR to XSD</span></span>|<span data-ttu-id="0c4ba-199">使用精简 XML 数据架构文件生成 XML 架构。</span><span class="sxs-lookup"><span data-stu-id="0c4ba-199">Generates an XML schema from an XML-Data-Reduced schema file.</span></span> <span data-ttu-id="0c4ba-200">XDR 为早期基于 XML 的架构格式。</span><span class="sxs-lookup"><span data-stu-id="0c4ba-200">XDR is an early XML-based schema format.</span></span>|
|<span data-ttu-id="0c4ba-201">XML 到 XSD</span><span class="sxs-lookup"><span data-stu-id="0c4ba-201">XML to XSD</span></span>|<span data-ttu-id="0c4ba-202">使用 XML 文件生成 XML 架构。</span><span class="sxs-lookup"><span data-stu-id="0c4ba-202">Generates an XML schema from an XML file.</span></span>|
|<span data-ttu-id="0c4ba-203">XSD 到 DataSet</span><span class="sxs-lookup"><span data-stu-id="0c4ba-203">XSD to DataSet</span></span>|<span data-ttu-id="0c4ba-204">使用 XSD 架构文件生成公共语言运行时 <xref:System.Data.DataSet> 类。</span><span class="sxs-lookup"><span data-stu-id="0c4ba-204">Generates common language runtime <xref:System.Data.DataSet> classes from an XSD schema file.</span></span> <span data-ttu-id="0c4ba-205">生成的类为规则 XML 数据提供复杂对象模型。</span><span class="sxs-lookup"><span data-stu-id="0c4ba-205">The generated classes provide a rich object model for regular XML data.</span></span>|
|<span data-ttu-id="0c4ba-206">XSD 到类</span><span class="sxs-lookup"><span data-stu-id="0c4ba-206">XSD to Classes</span></span>|<span data-ttu-id="0c4ba-207">使用 XSD 架构文件生成运行时类。</span><span class="sxs-lookup"><span data-stu-id="0c4ba-207">Generates runtime classes from an XSD schema file.</span></span> <span data-ttu-id="0c4ba-208">生成的类可以与 <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> 一起使用，来读写遵循该架构的 XML 代码。</span><span class="sxs-lookup"><span data-stu-id="0c4ba-208">The generated classes can be used in conjunction with <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> to read and write XML code that follows the schema.</span></span>|
|<span data-ttu-id="0c4ba-209">类到 XSD</span><span class="sxs-lookup"><span data-stu-id="0c4ba-209">Classes to XSD</span></span>| <span data-ttu-id="0c4ba-210">使用运行时程序集文件中的一个或多个类型生成 XML 架构。</span><span class="sxs-lookup"><span data-stu-id="0c4ba-210">Generates an XML schema from a type or types in a runtime assembly file.</span></span> <span data-ttu-id="0c4ba-211">生成的架构定义了 <xref:System.Xml.Serialization.XmlSerializer> 使用的 XML 格式。</span><span class="sxs-lookup"><span data-stu-id="0c4ba-211">The generated schema defines the XML format used by the <xref:System.Xml.Serialization.XmlSerializer>.</span></span>|

 <span data-ttu-id="0c4ba-212">Xsd.exe 只允许操作遵循由万维网联合会 (W3C) 提议的 XML 架构定义 (XSD) 语言的 XML 架构。</span><span class="sxs-lookup"><span data-stu-id="0c4ba-212">Xsd.exe only allows you to manipulate XML schemas that follow the XML Schema Definition (XSD) language proposed by the World Wide Web Consortium (W3C).</span></span> <span data-ttu-id="0c4ba-213">有关 XML 架构定义提议或 XML 标准的详细信息，请参阅 <https://w3.org>。</span><span class="sxs-lookup"><span data-stu-id="0c4ba-213">For more information on the XML Schema Definition proposal or the XML standard, see <https://w3.org>.</span></span>

## <a name="setting-options-with-an-xml-file"></a><span data-ttu-id="0c4ba-214">通过 XML 文件设置选项</span><span class="sxs-lookup"><span data-stu-id="0c4ba-214">Setting Options with an XML File</span></span>

<span data-ttu-id="0c4ba-215">通过使用 `/parameters` 开关，可指定设置各种选项的单个 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="0c4ba-215">By using the `/parameters` switch, you can specify a single XML file that sets various options.</span></span> <span data-ttu-id="0c4ba-216">可设置的选项取决于您如何使用 XSD.exe 工具。</span><span class="sxs-lookup"><span data-stu-id="0c4ba-216">The options you can set depend on how you are using the XSD.exe tool.</span></span> <span data-ttu-id="0c4ba-217">选择包括生成架构、生成代码文件，或生成包含 `DataSet` 功能的代码文件。</span><span class="sxs-lookup"><span data-stu-id="0c4ba-217">Choices include generating schemas, generating code files, or generating code files that include `DataSet` features.</span></span> <span data-ttu-id="0c4ba-218">例如，生成架构时可将 `<assembly>` 元素设置为可执行文件 (.exe) 或类库文件 (.dll) 的名称，但生成代码文件时则不能。</span><span class="sxs-lookup"><span data-stu-id="0c4ba-218">For example, you can set the `<assembly>` element to the name of an executable (.exe) or type library (.dll) file when generating a schema, but not when generating a code file.</span></span> <span data-ttu-id="0c4ba-219">下面的 XML 演示如何将 `<generateSchemas>` 元素用于指定的可执行文件：</span><span class="sxs-lookup"><span data-stu-id="0c4ba-219">The following XML shows how to use the `<generateSchemas>` element with a specified executable:</span></span>

```xml
<!-- This is in a file named GenerateSchemas.xml. -->
<xsd xmlns='http://microsoft.com/dotnet/tools/xsd/'>
<generateSchemas>
   <assembly>ConsoleApplication1.exe</assembly>
</generateSchemas>
</xsd>
```

<span data-ttu-id="0c4ba-220">如果前面的 XML 包含在名为 GenerateSchemas.xml 的文件中，则通过在命令提示处键入下面的内容并按 Enter 来使用 `/parameters` 开关  ：</span><span class="sxs-lookup"><span data-stu-id="0c4ba-220">If the preceding XML is contained in a file named GenerateSchemas.xml, then use the `/parameters` switch by typing the following at a command prompt and pressing **Enter**:</span></span>

```console
 xsd /p:GenerateSchemas.xml
```

<span data-ttu-id="0c4ba-221">另外，如果为程序集中的单个类型生成架构，则可以使用下面的 XML：</span><span class="sxs-lookup"><span data-stu-id="0c4ba-221">On the other hand, if you are generating a schema for a single type found in the assembly, you can use the following XML:</span></span>

```xml
<!-- This is in a file named GenerateSchemaFromType.xml. -->
<xsd xmlns='http://microsoft.com/dotnet/tools/xsd/'>
<generateSchemas>
   <type>IDItems</type>
</generateSchemas>
</xsd>
```

<span data-ttu-id="0c4ba-222">但是若要使用上面的代码，您还必须在命令提示处提供程序集的名称。</span><span class="sxs-lookup"><span data-stu-id="0c4ba-222">But to use preceding code, you must also supply the name of the assembly at the command prompt.</span></span> <span data-ttu-id="0c4ba-223">在命令提示处输入下面的内容（假设 XML 文件名为 GenerateSchemaFromType.xml）：</span><span class="sxs-lookup"><span data-stu-id="0c4ba-223">Enter the following at a command prompt (presuming the XML file is named GenerateSchemaFromType.xml):</span></span>

```console
xsd /p:GenerateSchemaFromType.xml ConsoleApplication1.exe
```

<span data-ttu-id="0c4ba-224">必须为 `<generateSchemas>` 元素仅指定以下选项中的一个。</span><span class="sxs-lookup"><span data-stu-id="0c4ba-224">You must specify only one of the following options for the `<generateSchemas>` element.</span></span>

|<span data-ttu-id="0c4ba-225">元素</span><span class="sxs-lookup"><span data-stu-id="0c4ba-225">Element</span></span>|<span data-ttu-id="0c4ba-226">描述</span><span class="sxs-lookup"><span data-stu-id="0c4ba-226">Description</span></span>|
|-------------|-----------------|
|<span data-ttu-id="0c4ba-227">\<assembly></span><span class="sxs-lookup"><span data-stu-id="0c4ba-227">\<assembly></span></span>|<span data-ttu-id="0c4ba-228">指定将从中生成架构的程序集。</span><span class="sxs-lookup"><span data-stu-id="0c4ba-228">Specifies an assembly to generate the schema from.</span></span>|
|<span data-ttu-id="0c4ba-229">\<type></span><span class="sxs-lookup"><span data-stu-id="0c4ba-229">\<type></span></span>|<span data-ttu-id="0c4ba-230">指定程序集中找到的要为其生成架构的类型。</span><span class="sxs-lookup"><span data-stu-id="0c4ba-230">Specifies a type found in an assembly to generate a schema for.</span></span>|
|<span data-ttu-id="0c4ba-231">\<xml></span><span class="sxs-lookup"><span data-stu-id="0c4ba-231">\<xml></span></span>|<span data-ttu-id="0c4ba-232">指定要为其生成架构的 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="0c4ba-232">Specifies an XML file to generate a schema for.</span></span>|
|<span data-ttu-id="0c4ba-233">\<xdr></span><span class="sxs-lookup"><span data-stu-id="0c4ba-233">\<xdr></span></span>|<span data-ttu-id="0c4ba-234">指定要为其生成架构的 XDR 文件。</span><span class="sxs-lookup"><span data-stu-id="0c4ba-234">Specifies an XDR file to generate a schema for.</span></span>|

<span data-ttu-id="0c4ba-235">若要生成代码文件，请使用 `<generateClasses>` 元素。</span><span class="sxs-lookup"><span data-stu-id="0c4ba-235">To generate a code file, use the `<generateClasses>` element.</span></span> <span data-ttu-id="0c4ba-236">下面的示例生成一个代码文件。</span><span class="sxs-lookup"><span data-stu-id="0c4ba-236">The following example generates a code file.</span></span> <span data-ttu-id="0c4ba-237">请注意，另外还显示了两个特性，它们允许您为生成的文件设置编程语言和命名空间。</span><span class="sxs-lookup"><span data-stu-id="0c4ba-237">Note that two attributes are also shown that allow you to set the programming language and namespace of the generated file.</span></span>

```xml
<xsd xmlns='http://microsoft.com/dotnet/tools/xsd/'>
<generateClasses language='VB' namespace='Microsoft.Serialization.Examples'/>
</xsd>
<!-- You must supply an .xsd file when typing in the command line.-->
<!-- For example: xsd /p:genClasses mySchema.xsd -->
```

 <span data-ttu-id="0c4ba-238">可为 `<generateClasses>` 元素设置以下选项。</span><span class="sxs-lookup"><span data-stu-id="0c4ba-238">Options you can set for the `<generateClasses>` element include the following.</span></span>

|<span data-ttu-id="0c4ba-239">元素</span><span class="sxs-lookup"><span data-stu-id="0c4ba-239">Element</span></span>|<span data-ttu-id="0c4ba-240">描述</span><span class="sxs-lookup"><span data-stu-id="0c4ba-240">Description</span></span>|
|-------------|-----------------|
|<span data-ttu-id="0c4ba-241">\<element></span><span class="sxs-lookup"><span data-stu-id="0c4ba-241">\<element></span></span>|<span data-ttu-id="0c4ba-242">指定 .xsd 文件中要为其生成代码的元素。</span><span class="sxs-lookup"><span data-stu-id="0c4ba-242">Specifies an element in the .xsd file to generate code for.</span></span>|
|<span data-ttu-id="0c4ba-243">\<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="0c4ba-243">\<schemaImporterExtensions></span></span>|<span data-ttu-id="0c4ba-244">指定派生自 <xref:System.Xml.Serialization.Advanced.SchemaImporterExtension> 类的类型。</span><span class="sxs-lookup"><span data-stu-id="0c4ba-244">Specifies a type derived from the <xref:System.Xml.Serialization.Advanced.SchemaImporterExtension> class.</span></span>|
|<span data-ttu-id="0c4ba-245">\<schema></span><span class="sxs-lookup"><span data-stu-id="0c4ba-245">\<schema></span></span>|<span data-ttu-id="0c4ba-246">指定要为其生成代码的 XML 架构文件。</span><span class="sxs-lookup"><span data-stu-id="0c4ba-246">Specifies a XML Schema file to generate code for.</span></span> <span data-ttu-id="0c4ba-247">可使用多个 \<schema> 元素指定多个 XML 架构文件。</span><span class="sxs-lookup"><span data-stu-id="0c4ba-247">Multiple XML Schema files can be specified using multiple \<schema> elements.</span></span>|

<span data-ttu-id="0c4ba-248">下表显示也可用于 `<generateClasses>` 元素的特性。</span><span class="sxs-lookup"><span data-stu-id="0c4ba-248">The following table shows the attributes that can also be used with the `<generateClasses>` element.</span></span>

|<span data-ttu-id="0c4ba-249">特性</span><span class="sxs-lookup"><span data-stu-id="0c4ba-249">Attribute</span></span>|<span data-ttu-id="0c4ba-250">描述</span><span class="sxs-lookup"><span data-stu-id="0c4ba-250">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="0c4ba-251">语言</span><span class="sxs-lookup"><span data-stu-id="0c4ba-251">language</span></span>|<span data-ttu-id="0c4ba-252">指定要使用的编程语言。</span><span class="sxs-lookup"><span data-stu-id="0c4ba-252">Specifies the programming language to use.</span></span> <span data-ttu-id="0c4ba-253">从 `CS`（默认情况下为 C#）、`VB` (Visual Basic)、`JS` (JScript) 或 `VJS` (Visual J#) 中进行选择。</span><span class="sxs-lookup"><span data-stu-id="0c4ba-253">Choose from `CS` (C#, the default), `VB` (Visual Basic), `JS` (JScript), or `VJS` (Visual J#).</span></span> <span data-ttu-id="0c4ba-254">也可指定实现 <xref:System.CodeDom.Compiler.CodeDomProvider> 的类的完全限定名。</span><span class="sxs-lookup"><span data-stu-id="0c4ba-254">You can also specify a fully qualified name for a class that implements <xref:System.CodeDom.Compiler.CodeDomProvider>.</span></span>|
|<span data-ttu-id="0c4ba-255">namespace</span><span class="sxs-lookup"><span data-stu-id="0c4ba-255">namespace</span></span>|<span data-ttu-id="0c4ba-256">为生成的代码指定命名空间。</span><span class="sxs-lookup"><span data-stu-id="0c4ba-256">Specifies the namespace for the generated code.</span></span> <span data-ttu-id="0c4ba-257">命名空间必须符合 CLR 标准（例如，没有空格或反斜杠字符）。</span><span class="sxs-lookup"><span data-stu-id="0c4ba-257">The namespace must conform to CLR standards (for example, no spaces or backslash characters).</span></span>|
|<span data-ttu-id="0c4ba-258">选项</span><span class="sxs-lookup"><span data-stu-id="0c4ba-258">options</span></span>|<span data-ttu-id="0c4ba-259">以下值之一：`none`、`properties`（生成属性而不是公共字段）、`order` 或 `enableDataBinding`（请参见前面“XSD 文件选项”一节的 `/order` 和 `/enableDataBinding` 开关）。</span><span class="sxs-lookup"><span data-stu-id="0c4ba-259">One of the following values: `none`, `properties` (generates properties instead of public fields), `order`, or `enableDataBinding` (see the `/order` and `/enableDataBinding` switches in the preceding XSD File Options section.</span></span>|

 <span data-ttu-id="0c4ba-260">使用 `DataSet` 元素还可以控制如何生成 `<generateDataSet>` 代码。</span><span class="sxs-lookup"><span data-stu-id="0c4ba-260">You can also control how `DataSet` code is generated by using the `<generateDataSet>` element.</span></span> <span data-ttu-id="0c4ba-261">下面的 XML 指定生成的代码使用 `DataSet` 结构（如 <xref:System.Data.DataTable> 类）为指定元素创建 Visual Basic 代码。</span><span class="sxs-lookup"><span data-stu-id="0c4ba-261">The following XML specifies that the generated code uses `DataSet` structures (such as the <xref:System.Data.DataTable> class) to create Visual Basic code for a specified element.</span></span> <span data-ttu-id="0c4ba-262">生成的数据集结构将支持 LINQ 查询。</span><span class="sxs-lookup"><span data-stu-id="0c4ba-262">The generated DataSet structures will support LINQ queries.</span></span>

 ```xml
 <xsd xmlns='http://microsoft.com/dotnet/tools/xsd/'>
     <generateDataSet language='VB' namespace='Microsoft.Serialization.Examples' enableLinqDataSet='true'>
     </generateDataSet>
 </xsd>
```

<span data-ttu-id="0c4ba-263">可为 `<generateDataSet>` 元素设置以下选项。</span><span class="sxs-lookup"><span data-stu-id="0c4ba-263">Options you can set for the `<generateDataSet>` element include the following.</span></span>

|<span data-ttu-id="0c4ba-264">元素</span><span class="sxs-lookup"><span data-stu-id="0c4ba-264">Element</span></span>|<span data-ttu-id="0c4ba-265">描述</span><span class="sxs-lookup"><span data-stu-id="0c4ba-265">Description</span></span>|
|-------------|-----------------|
|<span data-ttu-id="0c4ba-266">\<schema></span><span class="sxs-lookup"><span data-stu-id="0c4ba-266">\<schema></span></span>|<span data-ttu-id="0c4ba-267">指定要为其生成代码的 XML 架构文件。</span><span class="sxs-lookup"><span data-stu-id="0c4ba-267">Specifies an XML Schema file to generate code for.</span></span> <span data-ttu-id="0c4ba-268">可使用多个 \<schema> 元素指定多个 XML 架构文件。</span><span class="sxs-lookup"><span data-stu-id="0c4ba-268">Multiple XML Schema files can be specified using multiple \<schema> elements.</span></span>|

 <span data-ttu-id="0c4ba-269">下表显示可与 `<generateDataSet>` 元素一起使用的特性。</span><span class="sxs-lookup"><span data-stu-id="0c4ba-269">The following table shows the attributes that can be used with the `<generateDataSet>` element.</span></span>

|<span data-ttu-id="0c4ba-270">特性</span><span class="sxs-lookup"><span data-stu-id="0c4ba-270">Attribute</span></span>|<span data-ttu-id="0c4ba-271">描述</span><span class="sxs-lookup"><span data-stu-id="0c4ba-271">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="0c4ba-272">enableLinqDataSet</span><span class="sxs-lookup"><span data-stu-id="0c4ba-272">enableLinqDataSet</span></span>|<span data-ttu-id="0c4ba-273">指定可使用 LINQ to DataSet 查询的生成的数据集。</span><span class="sxs-lookup"><span data-stu-id="0c4ba-273">Specifies that the generated DataSet can be queried against using LINQ to DataSet.</span></span> <span data-ttu-id="0c4ba-274">默认值为 False。</span><span class="sxs-lookup"><span data-stu-id="0c4ba-274">The default value is false.</span></span>|
|<span data-ttu-id="0c4ba-275">语言</span><span class="sxs-lookup"><span data-stu-id="0c4ba-275">language</span></span>|<span data-ttu-id="0c4ba-276">指定要使用的编程语言。</span><span class="sxs-lookup"><span data-stu-id="0c4ba-276">Specifies the programming language to use.</span></span> <span data-ttu-id="0c4ba-277">从 `CS`（默认情况下为 C#）、`VB` (Visual Basic)、`JS` (JScript) 或 `VJS` (Visual J#) 中进行选择。</span><span class="sxs-lookup"><span data-stu-id="0c4ba-277">Choose from `CS` (C#, the default), `VB` (Visual Basic), `JS` (JScript), or `VJS` (Visual J#).</span></span> <span data-ttu-id="0c4ba-278">也可指定实现 <xref:System.CodeDom.Compiler.CodeDomProvider> 的类的完全限定名。</span><span class="sxs-lookup"><span data-stu-id="0c4ba-278">You can also specify a fully qualified name for a class that implements <xref:System.CodeDom.Compiler.CodeDomProvider>.</span></span>|
|<span data-ttu-id="0c4ba-279">namespace</span><span class="sxs-lookup"><span data-stu-id="0c4ba-279">namespace</span></span>|<span data-ttu-id="0c4ba-280">为生成的代码指定命名空间。</span><span class="sxs-lookup"><span data-stu-id="0c4ba-280">Specifies the namespace for the generated code.</span></span> <span data-ttu-id="0c4ba-281">命名空间必须符合 CLR 标准（例如，没有空格或反斜杠字符）。</span><span class="sxs-lookup"><span data-stu-id="0c4ba-281">The namespace must conform to CLR standards (for example, no spaces or backslash characters).</span></span>|

 <span data-ttu-id="0c4ba-282">有些特性可在顶级 `<xsd>` 元素上设置。</span><span class="sxs-lookup"><span data-stu-id="0c4ba-282">There are attributes that you can set on the top level `<xsd>` element.</span></span> <span data-ttu-id="0c4ba-283">这些选项可用于任何子元素（`<generateSchemas>`、`<generateClasses>` 或 `<generateDataSet>`）。</span><span class="sxs-lookup"><span data-stu-id="0c4ba-283">These options can be used with any of the child elements (`<generateSchemas>`, `<generateClasses>` or `<generateDataSet>`).</span></span> <span data-ttu-id="0c4ba-284">下面的 XML 代码在名为“MyOutputDirectory”的输出目录中为名为“IDItems”的元素生成代码。</span><span class="sxs-lookup"><span data-stu-id="0c4ba-284">The following XML code generates code for an element named "IDItems" in the output directory named "MyOutputDirectory".</span></span>

```xml
<xsd xmlns='http://microsoft.com/dotnet/tools/xsd/' output='MyOutputDirectory'>
<generateClasses>
    <element>IDItems</element>
</generateClasses>
</xsd>
```

<span data-ttu-id="0c4ba-285">下表显示也可用于 `<xsd>` 元素的特性。</span><span class="sxs-lookup"><span data-stu-id="0c4ba-285">The following table shows the attributes that can also be used with the `<xsd>` element.</span></span>

|<span data-ttu-id="0c4ba-286">特性</span><span class="sxs-lookup"><span data-stu-id="0c4ba-286">Attribute</span></span>|<span data-ttu-id="0c4ba-287">描述</span><span class="sxs-lookup"><span data-stu-id="0c4ba-287">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="0c4ba-288">输出</span><span class="sxs-lookup"><span data-stu-id="0c4ba-288">output</span></span>|<span data-ttu-id="0c4ba-289">将放置生成的架构或代码文件的目录的名称。</span><span class="sxs-lookup"><span data-stu-id="0c4ba-289">The name of a directory where the generated schema or code file will be placed.</span></span>|
|<span data-ttu-id="0c4ba-290">nologo</span><span class="sxs-lookup"><span data-stu-id="0c4ba-290">nologo</span></span>|<span data-ttu-id="0c4ba-291">取消显示版权标志。</span><span class="sxs-lookup"><span data-stu-id="0c4ba-291">Suppresses the banner.</span></span> <span data-ttu-id="0c4ba-292">设置为 `true` 或 `false`。</span><span class="sxs-lookup"><span data-stu-id="0c4ba-292">Set to `true` or `false`.</span></span>|
|<span data-ttu-id="0c4ba-293">帮助</span><span class="sxs-lookup"><span data-stu-id="0c4ba-293">help</span></span>|<span data-ttu-id="0c4ba-294">显示该工具的命令语法和选项。</span><span class="sxs-lookup"><span data-stu-id="0c4ba-294">Displays command syntax and options for the tool.</span></span> <span data-ttu-id="0c4ba-295">设置为 `true` 或 `false`。</span><span class="sxs-lookup"><span data-stu-id="0c4ba-295">Set to `true` or `false`.</span></span>|

## <a name="examples"></a><span data-ttu-id="0c4ba-296">示例</span><span class="sxs-lookup"><span data-stu-id="0c4ba-296">Examples</span></span>
 <span data-ttu-id="0c4ba-297">下面的命令从 `myFile.xdr` 生成一个 XML 架构并将它保存到当前目录中。</span><span class="sxs-lookup"><span data-stu-id="0c4ba-297">The following command generates an XML schema from `myFile.xdr` and saves it to the current directory.</span></span>

```console
xsd myFile.xdr
```

<span data-ttu-id="0c4ba-298">下面的命令从 `myFile.xml` 生成一个 XML 架构并将它保存到指定目录中。</span><span class="sxs-lookup"><span data-stu-id="0c4ba-298">The following command generates an XML schema from `myFile.xml` and saves it to the specified directory.</span></span>

```console
xsd myFile.xml /outputdir:myOutputDir
```

<span data-ttu-id="0c4ba-299">下面的命令生成一个与 C# 语言中的指定架构相对应的数据集，并在当前目录中将其保存为 `XSDSchemaFile.cs`。</span><span class="sxs-lookup"><span data-stu-id="0c4ba-299">The following command generates a data set that corresponds to the specified schema in the C# language and saves it as `XSDSchemaFile.cs` in the current directory.</span></span>

```console
xsd /dataset /language:CS XSDSchemaFile.xsd
```

<span data-ttu-id="0c4ba-300">下面的命令为程序集 `myAssembly.dll` 中的所有类型生成 XML 架构，并在当前目录中将它们保存为 `schema0.xsd`。</span><span class="sxs-lookup"><span data-stu-id="0c4ba-300">The following command generates XML schemas for all types in the assembly `myAssembly.dll` and saves them as `schema0.xsd` in the current directory.</span></span>

```console
xsd myAssembly.dll
```

## <a name="see-also"></a><span data-ttu-id="0c4ba-301">请参阅</span><span class="sxs-lookup"><span data-stu-id="0c4ba-301">See also</span></span>

- <xref:System.Data.DataSet>
- <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType>
- [<span data-ttu-id="0c4ba-302">工具</span><span class="sxs-lookup"><span data-stu-id="0c4ba-302">Tools</span></span>](../../../docs/framework/tools/index.md)
- [<span data-ttu-id="0c4ba-303">命令提示</span><span class="sxs-lookup"><span data-stu-id="0c4ba-303">Command Prompts</span></span>](../../../docs/framework/tools/developer-command-prompt-for-vs.md)
- [<span data-ttu-id="0c4ba-304">LINQ to DataSet 概述</span><span class="sxs-lookup"><span data-stu-id="0c4ba-304">LINQ to DataSet Overview</span></span>](../../../docs/framework/data/adonet/linq-to-dataset-overview.md)
- [<span data-ttu-id="0c4ba-305">查询类型化数据集</span><span class="sxs-lookup"><span data-stu-id="0c4ba-305">Querying Typed DataSets</span></span>](../../../docs/framework/data/adonet/querying-typed-datasets.md)
- [<span data-ttu-id="0c4ba-306">LINQ（语言集成查询）(C#)</span><span class="sxs-lookup"><span data-stu-id="0c4ba-306">LINQ (Language-Integrated Query) (C#)</span></span>](../../csharp/programming-guide/concepts/linq/index.md)
- [<span data-ttu-id="0c4ba-307">LINQ（语言集成查询）(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0c4ba-307">LINQ (Language-Integrated Query) (Visual Basic)</span></span>](../../visual-basic/programming-guide/concepts/linq/index.md)
