---
title: XML Schema Definition Tool (Xsd.exe)
ms.date: 03/30/2017
ms.assetid: a6e6e65c-347f-4494-9457-653bf29baac2
ms.openlocfilehash: cd017eb1866fff2ce8fd7a858b184351ef13e815
ms.sourcegitcommit: 961ec21c22d2f1d55c9cc8a7edf2ade1d1fd92e3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2020
ms.locfileid: "80588352"
---
# <a name="xml-schema-definition-tool-xsdexe"></a><span data-ttu-id="17800-102">XML Schema Definition Tool (Xsd.exe)</span><span class="sxs-lookup"><span data-stu-id="17800-102">XML Schema Definition Tool (Xsd.exe)</span></span>

<span data-ttu-id="17800-103">XML 架构定义 (Xsd.exe) 工具从 XDR、XML 和 XSD 文件或者从运行时程序集中的类生成 XML 架构或公共语言运行时类。</span><span class="sxs-lookup"><span data-stu-id="17800-103">The XML Schema Definition (Xsd.exe) tool generates XML schema or common language runtime classes from XDR, XML, and XSD files, or from classes in a runtime assembly.</span></span>

## <a name="syntax"></a><span data-ttu-id="17800-104">语法</span><span class="sxs-lookup"><span data-stu-id="17800-104">Syntax</span></span>

<span data-ttu-id="17800-105">从命令行运行该工具。</span><span class="sxs-lookup"><span data-stu-id="17800-105">Run the tool from the command line.</span></span>

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
> <span data-ttu-id="17800-106">对于 .NET 框架工具要正常运行，必须正确设置`Path` `Include`、`Lib`和环境变量。</span><span class="sxs-lookup"><span data-stu-id="17800-106">For .NET Framework tools to function properly, you must set your `Path`, `Include`, and `Lib` environment variables correctly.</span></span> <span data-ttu-id="17800-107">可以通过运行 SDKVars.bat（位于 \<SDK>\v2.0\Bin 目录中）来设置这些环境变量。</span><span class="sxs-lookup"><span data-stu-id="17800-107">Set these environment variables by running SDKVars.bat, which is located in the \<SDK>\v2.0\Bin directory.</span></span> <span data-ttu-id="17800-108">必须在每个命令 shell 程序中执行 SDKVars.bat。</span><span class="sxs-lookup"><span data-stu-id="17800-108">SDKVars.bat must be executed in every command shell.</span></span>

## <a name="argument"></a><span data-ttu-id="17800-109">参数</span><span class="sxs-lookup"><span data-stu-id="17800-109">Argument</span></span>

|<span data-ttu-id="17800-110">参数</span><span class="sxs-lookup"><span data-stu-id="17800-110">Argument</span></span>|<span data-ttu-id="17800-111">描述</span><span class="sxs-lookup"><span data-stu-id="17800-111">Description</span></span>|
|--------------|-----------------|
|<span data-ttu-id="17800-112">*文件.扩展名*</span><span class="sxs-lookup"><span data-stu-id="17800-112">*file.extension*</span></span>|<span data-ttu-id="17800-113">指定要转换的输入文件。</span><span class="sxs-lookup"><span data-stu-id="17800-113">Specifies the input file to convert.</span></span> <span data-ttu-id="17800-114">必须将扩展指定为以下项之一：.xdr、.xml、.xsd、.dll 或 .exe。</span><span class="sxs-lookup"><span data-stu-id="17800-114">You must specify the extension as one of the following: .xdr, .xml, .xsd, .dll, or .exe.</span></span><br /><br /> <span data-ttu-id="17800-115">如果指定一个 XDR 架构文件（.xdr 扩展名），则 Xsd.exe 将 XDR 架构转换为 XSD 架构。</span><span class="sxs-lookup"><span data-stu-id="17800-115">If you specify an XDR schema file (.xdr extension), Xsd.exe converts the XDR schema to an XSD schema.</span></span> <span data-ttu-id="17800-116">输出文件与 XDR 架构同名，但扩展名为 .xsd。</span><span class="sxs-lookup"><span data-stu-id="17800-116">The output file has the same name as the XDR schema, but with the .xsd extension.</span></span><br /><br /> <span data-ttu-id="17800-117">如果指定一个 XML 文件（.xml 扩展名），则 Xsd.exe 从文件中的数据推导出架构并产生一个 XSD 架构。</span><span class="sxs-lookup"><span data-stu-id="17800-117">If you specify an XML file (.xml extension), Xsd.exe infers a schema from the data in the file and produces an XSD schema.</span></span> <span data-ttu-id="17800-118">输出文件与 XML 文件同名，但扩展名为 .xsd。</span><span class="sxs-lookup"><span data-stu-id="17800-118">The output file has the same name as the XML file, but with the .xsd extension.</span></span><br /><br /> <span data-ttu-id="17800-119">如果指定一个 XML 架构文件（.xsd 扩展名），则 Xsd.exe 将为对应于 XML 架构的运行时对象生成源代码。</span><span class="sxs-lookup"><span data-stu-id="17800-119">If you specify an XML schema file (.xsd extension), Xsd.exe generates source code for runtime objects that correspond to the XML schema.</span></span><br /><br /> <span data-ttu-id="17800-120">如果指定一个运行时程序集文件（.exe 或 .dll 扩展名），则 Xsd.exe 为该程序集中的一个或多个类型生成架构。</span><span class="sxs-lookup"><span data-stu-id="17800-120">If you specify a runtime assembly file (.exe or .dll extension), Xsd.exe generates schemas for one or more types in that assembly.</span></span> <span data-ttu-id="17800-121">可以使用 `/type` 选项来指定为其生成架构的类型。</span><span class="sxs-lookup"><span data-stu-id="17800-121">You can use the `/type` option to specify the types for which to generate schemas.</span></span> <span data-ttu-id="17800-122">输出架构被命名为 schema0.xsd、schema1.xsd，依此类推。</span><span class="sxs-lookup"><span data-stu-id="17800-122">The output schemas are named schema0.xsd, schema1.xsd, and so on.</span></span> <span data-ttu-id="17800-123">仅当给定类型使用 `XMLRoot` 自定义特性指定命名空间时，Xsd.exe 才生成多个架构。</span><span class="sxs-lookup"><span data-stu-id="17800-123">Xsd.exe produces multiple schemas only if the given types specify a namespace using the `XMLRoot` custom attribute.</span></span>|

## <a name="general-options"></a><span data-ttu-id="17800-124">常规选项</span><span class="sxs-lookup"><span data-stu-id="17800-124">General Options</span></span>

|<span data-ttu-id="17800-125">选项</span><span class="sxs-lookup"><span data-stu-id="17800-125">Option</span></span>|<span data-ttu-id="17800-126">描述</span><span class="sxs-lookup"><span data-stu-id="17800-126">Description</span></span>|
|------------|-----------------|
|<span data-ttu-id="17800-127">**/h\[埃尔普\]**</span><span class="sxs-lookup"><span data-stu-id="17800-127">**/h\[elp\]**</span></span>|<span data-ttu-id="17800-128">显示该工具的命令语法和选项。</span><span class="sxs-lookup"><span data-stu-id="17800-128">Displays command syntax and options for the tool.</span></span>|
|<span data-ttu-id="17800-129">**/o\[乌普特\]迪尔 ：**_目录_</span><span class="sxs-lookup"><span data-stu-id="17800-129">**/o\[utputdir\]:**_directory_</span></span>|<span data-ttu-id="17800-130">指定输出文件的目录。</span><span class="sxs-lookup"><span data-stu-id="17800-130">Specifies the directory for output files.</span></span> <span data-ttu-id="17800-131">此参数只能出现一次。</span><span class="sxs-lookup"><span data-stu-id="17800-131">This argument can appear only once.</span></span> <span data-ttu-id="17800-132">默认值为当前目录。</span><span class="sxs-lookup"><span data-stu-id="17800-132">The default is the current directory.</span></span>|
|<span data-ttu-id="17800-133">**/?**</span><span class="sxs-lookup"><span data-stu-id="17800-133">**/?**</span></span>|<span data-ttu-id="17800-134">显示该工具的命令语法和选项。</span><span class="sxs-lookup"><span data-stu-id="17800-134">Displays command syntax and options for the tool.</span></span>|
|<span data-ttu-id="17800-135">**/p\[阿拉\]米 ：**_文件.xml_</span><span class="sxs-lookup"><span data-stu-id="17800-135">**/p\[arameters\]:**_file.xml_</span></span>|<span data-ttu-id="17800-136">从指定的 .xml 文件读取各种操作模式的选项。</span><span class="sxs-lookup"><span data-stu-id="17800-136">Read options for various operation modes from the specified .xml file.</span></span> <span data-ttu-id="17800-137">缩写形式为 `/p:`。</span><span class="sxs-lookup"><span data-stu-id="17800-137">The short form is `/p:`.</span></span> <span data-ttu-id="17800-138">有关详细信息，请参阅[备注](#remarks)部分。</span><span class="sxs-lookup"><span data-stu-id="17800-138">For more information, see the [Remarks](#remarks) section.</span></span>|

## <a name="xsd-file-options"></a><span data-ttu-id="17800-139">XSD 文件选项</span><span class="sxs-lookup"><span data-stu-id="17800-139">XSD File Options</span></span>
 <span data-ttu-id="17800-140">必须为 xsd 文件仅指定下列选项中的一个。</span><span class="sxs-lookup"><span data-stu-id="17800-140">You must specify only one of the following options for .xsd files.</span></span>

|<span data-ttu-id="17800-141">选项</span><span class="sxs-lookup"><span data-stu-id="17800-141">Option</span></span>|<span data-ttu-id="17800-142">描述</span><span class="sxs-lookup"><span data-stu-id="17800-142">Description</span></span>|
|------------|-----------------|
|<span data-ttu-id="17800-143">**/c\[拉塞斯\]**</span><span class="sxs-lookup"><span data-stu-id="17800-143">**/c\[lasses\]**</span></span>|<span data-ttu-id="17800-144">生成与指定架构相对应的类。</span><span class="sxs-lookup"><span data-stu-id="17800-144">Generates classes that correspond to the specified schema.</span></span> <span data-ttu-id="17800-145">若要将 XML 数据读入对象中，请使用 <xref:System.Xml.Serialization.XmlSerializer.Deserialize%2A?displayProperty=nameWithType> 方法。</span><span class="sxs-lookup"><span data-stu-id="17800-145">To read XML data into the object, use the <xref:System.Xml.Serialization.XmlSerializer.Deserialize%2A?displayProperty=nameWithType> method.</span></span>|
|<span data-ttu-id="17800-146">**/d\[ataset\]**</span><span class="sxs-lookup"><span data-stu-id="17800-146">**/d\[ataset\]**</span></span>|<span data-ttu-id="17800-147">生成一个从 <xref:System.Data.DataSet> 派生的类，该类与指定的架构相对应。</span><span class="sxs-lookup"><span data-stu-id="17800-147">Generates a class derived from <xref:System.Data.DataSet> that corresponds to the specified schema.</span></span> <span data-ttu-id="17800-148">若要将 XML 数据读入派生类中，请使用 <xref:System.Data.DataSet.ReadXml%2A?displayProperty=nameWithType> 方法。</span><span class="sxs-lookup"><span data-stu-id="17800-148">To read XML data into the derived class, use the <xref:System.Data.DataSet.ReadXml%2A?displayProperty=nameWithType> method.</span></span>|

 <span data-ttu-id="17800-149">还可以为 .xsd 文件指定下列任何选项。</span><span class="sxs-lookup"><span data-stu-id="17800-149">You can also specify any of the following options for .xsd files.</span></span>

|<span data-ttu-id="17800-150">选项</span><span class="sxs-lookup"><span data-stu-id="17800-150">Option</span></span>|<span data-ttu-id="17800-151">描述</span><span class="sxs-lookup"><span data-stu-id="17800-151">Description</span></span>|
|------------|-----------------|
|<span data-ttu-id="17800-152">**/e\[娱乐\]：**_元素_</span><span class="sxs-lookup"><span data-stu-id="17800-152">**/e\[lement\]:**_element_</span></span>|<span data-ttu-id="17800-153">指定架构中要为其生成代码的元素。</span><span class="sxs-lookup"><span data-stu-id="17800-153">Specifies the element in the schema to generate code for.</span></span> <span data-ttu-id="17800-154">默认情况下，键入所有元素。</span><span class="sxs-lookup"><span data-stu-id="17800-154">By default all elements are typed.</span></span> <span data-ttu-id="17800-155">可以多次指定该参数。</span><span class="sxs-lookup"><span data-stu-id="17800-155">You can specify this argument more than once.</span></span>|
|<span data-ttu-id="17800-156">**/enableDataBinding**</span><span class="sxs-lookup"><span data-stu-id="17800-156">**/enableDataBinding**</span></span>|<span data-ttu-id="17800-157">在所有生成的类型上实现 <xref:System.ComponentModel.INotifyPropertyChanged> 接口以启用数据绑定。</span><span class="sxs-lookup"><span data-stu-id="17800-157">Implements the <xref:System.ComponentModel.INotifyPropertyChanged> interface on all generated types to enable data binding.</span></span> <span data-ttu-id="17800-158">缩写形式为 `/edb`。</span><span class="sxs-lookup"><span data-stu-id="17800-158">The short form is `/edb`.</span></span>|
|<span data-ttu-id="17800-159">**/启用 Linq 数据集**</span><span class="sxs-lookup"><span data-stu-id="17800-159">**/enableLinqDataSet**</span></span>|<span data-ttu-id="17800-160">（短形式： `/eld`.）指定可以使用 LINQ 到数据集查询生成的数据集。</span><span class="sxs-lookup"><span data-stu-id="17800-160">(Short form: `/eld`.) Specifies that the generated DataSet can be queried against using LINQ to DataSet.</span></span> <span data-ttu-id="17800-161">此选项在同时指定 /dataset 选项的情况下使用。</span><span class="sxs-lookup"><span data-stu-id="17800-161">This option is used when the /dataset option is also specified.</span></span> <span data-ttu-id="17800-162">有关详细信息，请参阅 [LINQ to DataSet 概述](../../../docs/framework/data/adonet/linq-to-dataset-overview.md)和[查询类型化数据集](../../../docs/framework/data/adonet/querying-typed-datasets.md)。</span><span class="sxs-lookup"><span data-stu-id="17800-162">For more information, see [LINQ to DataSet Overview](../../../docs/framework/data/adonet/linq-to-dataset-overview.md) and [Querying Typed DataSets](../../../docs/framework/data/adonet/querying-typed-datasets.md).</span></span> <span data-ttu-id="17800-163">有关使用 LINQ 的一般信息，请参阅[语言集成查询 （LINQ） - C#](../../csharp/programming-guide/concepts/linq/index.md)或[语言集成查询 （LINQ） - 可视基本](../../visual-basic/programming-guide/concepts/linq/index.md)。</span><span class="sxs-lookup"><span data-stu-id="17800-163">For general information about using LINQ, see [Language-Integrated Query (LINQ) - C#](../../csharp/programming-guide/concepts/linq/index.md) or [Language-Integrated Query (LINQ) - Visual Basic](../../visual-basic/programming-guide/concepts/linq/index.md).</span></span>|
|<span data-ttu-id="17800-164">**/f\[埃尔德斯\]**</span><span class="sxs-lookup"><span data-stu-id="17800-164">**/f\[ields\]**</span></span>|<span data-ttu-id="17800-165">生成字段，而不是生成属性。</span><span class="sxs-lookup"><span data-stu-id="17800-165">Generates fields instead of properties.</span></span> <span data-ttu-id="17800-166">默认情况下生成属性。</span><span class="sxs-lookup"><span data-stu-id="17800-166">By default, properties are generated.</span></span>|
|<span data-ttu-id="17800-167">**/l\[\]aguage ：**_语言_</span><span class="sxs-lookup"><span data-stu-id="17800-167">**/l\[anguage\]:**_language_</span></span>|<span data-ttu-id="17800-168">指定要使用的编程语言。</span><span class="sxs-lookup"><span data-stu-id="17800-168">Specifies the programming language to use.</span></span> <span data-ttu-id="17800-169">从 `CS`（默认情况下为 C#）、`VB` (Visual Basic)、`JS` (JScript) 或 `VJS` (Visual J#) 中进行选择。</span><span class="sxs-lookup"><span data-stu-id="17800-169">Choose from `CS` (C#, which is the default), `VB` (Visual Basic), `JS` (JScript), or `VJS` (Visual J#).</span></span> <span data-ttu-id="17800-170">也可指定实现 <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType> 的类的完全限定名</span><span class="sxs-lookup"><span data-stu-id="17800-170">You can also specify a fully qualified name for a class implementing <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType></span></span>|
|<span data-ttu-id="17800-171">**/n\[amespace\]：**_命名空间_</span><span class="sxs-lookup"><span data-stu-id="17800-171">**/n\[amespace\]:**_namespace_</span></span>|<span data-ttu-id="17800-172">为生成的类型指定运行时命名空间。</span><span class="sxs-lookup"><span data-stu-id="17800-172">Specifies the runtime namespace for the generated types.</span></span> <span data-ttu-id="17800-173">默认命名空间为 `Schemas`。</span><span class="sxs-lookup"><span data-stu-id="17800-173">The default namespace is `Schemas`.</span></span>|
|<span data-ttu-id="17800-174">**/nologo**</span><span class="sxs-lookup"><span data-stu-id="17800-174">**/nologo**</span></span>|<span data-ttu-id="17800-175">取消显示版权标志。</span><span class="sxs-lookup"><span data-stu-id="17800-175">Suppresses the banner.</span></span>|
|<span data-ttu-id="17800-176">**/订单**</span><span class="sxs-lookup"><span data-stu-id="17800-176">**/order**</span></span>|<span data-ttu-id="17800-177">在所有粒子成员上生成显式顺序标识符。</span><span class="sxs-lookup"><span data-stu-id="17800-177">Generates explicit order identifiers on all particle members.</span></span>|
|<span data-ttu-id="17800-178">**/o\[\]ut ：**_目录名称_</span><span class="sxs-lookup"><span data-stu-id="17800-178">**/o\[ut\]:**_directoryName_</span></span>|<span data-ttu-id="17800-179">指定用来放置文件的输出目录。</span><span class="sxs-lookup"><span data-stu-id="17800-179">Specifies the output directory to place the files in.</span></span> <span data-ttu-id="17800-180">默认值为当前目录。</span><span class="sxs-lookup"><span data-stu-id="17800-180">The default is the current directory.</span></span>|
|<span data-ttu-id="17800-181">**/u\[\]ri ：**_uri_</span><span class="sxs-lookup"><span data-stu-id="17800-181">**/u\[ri\]:**_uri_</span></span>|<span data-ttu-id="17800-182">为架构中要为其生成代码的元素指定 URI。</span><span class="sxs-lookup"><span data-stu-id="17800-182">Specifies the URI for the elements in the schema to generate code for.</span></span> <span data-ttu-id="17800-183">该 URI（如果存在）应用于使用 `/element` 选项指定的所有元素。</span><span class="sxs-lookup"><span data-stu-id="17800-183">This URI, if present, applies to all elements specified with the `/element` option.</span></span>|

## <a name="dll-and-exe-file-options"></a><span data-ttu-id="17800-184">DLL 和 EXE 文件选项</span><span class="sxs-lookup"><span data-stu-id="17800-184">DLL and EXE File Options</span></span>

|<span data-ttu-id="17800-185">选项</span><span class="sxs-lookup"><span data-stu-id="17800-185">Option</span></span>|<span data-ttu-id="17800-186">描述</span><span class="sxs-lookup"><span data-stu-id="17800-186">Description</span></span>|
|------------|-----------------|
|<span data-ttu-id="17800-187">**/t\[ype\]：**_类型名称_</span><span class="sxs-lookup"><span data-stu-id="17800-187">**/t\[ype\]:**_typename_</span></span>|<span data-ttu-id="17800-188">指定要为其创建架构的类型的名称。</span><span class="sxs-lookup"><span data-stu-id="17800-188">Specifies the name of the type to create a schema for.</span></span> <span data-ttu-id="17800-189">可以指定多个类型参数。</span><span class="sxs-lookup"><span data-stu-id="17800-189">You can specify multiple type arguments.</span></span> <span data-ttu-id="17800-190">如果 typename 不指定一个命名空间，则 Xsd.exe 将程序集中的所有类型与指定类型相匹配\*\*。</span><span class="sxs-lookup"><span data-stu-id="17800-190">If *typename* does not specify a namespace, Xsd.exe matches all types in the assembly with the specified type.</span></span> <span data-ttu-id="17800-191">如果 typename 指定一个命名空间，则仅匹配那个类型\*\*。</span><span class="sxs-lookup"><span data-stu-id="17800-191">If *typename* specifies a namespace, only that type is matched.</span></span> <span data-ttu-id="17800-192">如果 typename 以星号字符 (\*) 结尾，则此工具匹配所有以 \* 前的字符串开头的类型\*\*。</span><span class="sxs-lookup"><span data-stu-id="17800-192">If *typename* ends with an asterisk character (\*), the tool matches all types that start with the string preceding the \*.</span></span> <span data-ttu-id="17800-193">如果省略 `/type` 选项，则 Xsd.exe 为程序集中的所有类型生成架构。</span><span class="sxs-lookup"><span data-stu-id="17800-193">If you omit the `/type` option, Xsd.exe generates schemas for all types in the assembly.</span></span>|

## <a name="remarks"></a><span data-ttu-id="17800-194">备注</span><span class="sxs-lookup"><span data-stu-id="17800-194">Remarks</span></span>

<span data-ttu-id="17800-195">下表显示了 Xsd.exe 执行的操作。</span><span class="sxs-lookup"><span data-stu-id="17800-195">The following table shows the operations that Xsd.exe performs.</span></span>

| | |
|------------|-----------------|
|<span data-ttu-id="17800-196">XDR 到 XSD</span><span class="sxs-lookup"><span data-stu-id="17800-196">XDR to XSD</span></span>|<span data-ttu-id="17800-197">使用精简 XML 数据架构文件生成 XML 架构。</span><span class="sxs-lookup"><span data-stu-id="17800-197">Generates an XML schema from an XML-Data-Reduced schema file.</span></span> <span data-ttu-id="17800-198">XDR 为早期基于 XML 的架构格式。</span><span class="sxs-lookup"><span data-stu-id="17800-198">XDR is an early XML-based schema format.</span></span>|
|<span data-ttu-id="17800-199">XML 到 XSD</span><span class="sxs-lookup"><span data-stu-id="17800-199">XML to XSD</span></span>|<span data-ttu-id="17800-200">使用 XML 文件生成 XML 架构。</span><span class="sxs-lookup"><span data-stu-id="17800-200">Generates an XML schema from an XML file.</span></span>|
|<span data-ttu-id="17800-201">XSD 到 DataSet</span><span class="sxs-lookup"><span data-stu-id="17800-201">XSD to DataSet</span></span>|<span data-ttu-id="17800-202">使用 XSD 架构文件生成公共语言运行时 <xref:System.Data.DataSet> 类。</span><span class="sxs-lookup"><span data-stu-id="17800-202">Generates common language runtime <xref:System.Data.DataSet> classes from an XSD schema file.</span></span> <span data-ttu-id="17800-203">生成的类为规则 XML 数据提供复杂对象模型。</span><span class="sxs-lookup"><span data-stu-id="17800-203">The generated classes provide a rich object model for regular XML data.</span></span>|
|<span data-ttu-id="17800-204">XSD 到类</span><span class="sxs-lookup"><span data-stu-id="17800-204">XSD to Classes</span></span>|<span data-ttu-id="17800-205">使用 XSD 架构文件生成运行时类。</span><span class="sxs-lookup"><span data-stu-id="17800-205">Generates runtime classes from an XSD schema file.</span></span> <span data-ttu-id="17800-206">生成的类可以与 <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> 一起使用，来读写遵循该架构的 XML 代码。</span><span class="sxs-lookup"><span data-stu-id="17800-206">The generated classes can be used in conjunction with <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> to read and write XML code that follows the schema.</span></span>|
|<span data-ttu-id="17800-207">类到 XSD</span><span class="sxs-lookup"><span data-stu-id="17800-207">Classes to XSD</span></span>| <span data-ttu-id="17800-208">使用运行时程序集文件中的一个或多个类型生成 XML 架构。</span><span class="sxs-lookup"><span data-stu-id="17800-208">Generates an XML schema from a type or types in a runtime assembly file.</span></span> <span data-ttu-id="17800-209">生成的架构定义 的<xref:System.Xml.Serialization.XmlSerializer>XML 格式。</span><span class="sxs-lookup"><span data-stu-id="17800-209">The generated schema defines the XML format used by the <xref:System.Xml.Serialization.XmlSerializer>.</span></span>|

 <span data-ttu-id="17800-210">Xsd.exe 只允许操作遵循由万维网联合会 (W3C) 提议的 XML 架构定义 (XSD) 语言的 XML 架构。</span><span class="sxs-lookup"><span data-stu-id="17800-210">Xsd.exe only allows you to manipulate XML schemas that follow the XML Schema Definition (XSD) language proposed by the World Wide Web Consortium (W3C).</span></span> <span data-ttu-id="17800-211">有关 XML 架构定义建议或 XML 标准的详细信息，请参阅<https://w3.org>。</span><span class="sxs-lookup"><span data-stu-id="17800-211">For more information on the XML Schema Definition proposal or the XML standard, see <https://w3.org>.</span></span>

## <a name="setting-options-with-an-xml-file"></a><span data-ttu-id="17800-212">通过 XML 文件设置选项</span><span class="sxs-lookup"><span data-stu-id="17800-212">Setting Options with an XML File</span></span>

<span data-ttu-id="17800-213">通过使用 `/parameters` 开关，可指定设置各种选项的单个 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="17800-213">By using the `/parameters` switch, you can specify a single XML file that sets various options.</span></span> <span data-ttu-id="17800-214">可设置的选项取决于您如何使用 XSD.exe 工具。</span><span class="sxs-lookup"><span data-stu-id="17800-214">The options you can set depend on how you are using the XSD.exe tool.</span></span> <span data-ttu-id="17800-215">选择包括生成架构、生成代码文件，或生成包含 `DataSet` 功能的代码文件。</span><span class="sxs-lookup"><span data-stu-id="17800-215">Choices include generating schemas, generating code files, or generating code files that include `DataSet` features.</span></span> <span data-ttu-id="17800-216">例如，生成架构时可将 `<assembly>` 元素设置为可执行文件 (.exe) 或类库文件 (.dll) 的名称，但生成代码文件时则不能。</span><span class="sxs-lookup"><span data-stu-id="17800-216">For example, you can set the `<assembly>` element to the name of an executable (.exe) or type library (.dll) file when generating a schema, but not when generating a code file.</span></span> <span data-ttu-id="17800-217">下面的 XML 演示如何将 `<generateSchemas>` 元素用于指定的可执行文件：</span><span class="sxs-lookup"><span data-stu-id="17800-217">The following XML shows how to use the `<generateSchemas>` element with a specified executable:</span></span>

```xml
<!-- This is in a file named GenerateSchemas.xml. -->
<xsd xmlns='http://microsoft.com/dotnet/tools/xsd/'>
<generateSchemas>
   <assembly>ConsoleApplication1.exe</assembly>
</generateSchemas>
</xsd>
```

<span data-ttu-id="17800-218">如果前面的 XML 包含在名为 GenerateSchemas.xml 的文件中，则通过在`/parameters`命令提示符处键入以下内容并按**Enter**：</span><span class="sxs-lookup"><span data-stu-id="17800-218">If the preceding XML is contained in a file named GenerateSchemas.xml, then use the `/parameters` switch by typing the following at a command prompt and pressing **Enter**:</span></span>

```console
 xsd /p:GenerateSchemas.xml
```

<span data-ttu-id="17800-219">另外，如果为程序集中的单个类型生成架构，则可以使用下面的 XML：</span><span class="sxs-lookup"><span data-stu-id="17800-219">On the other hand, if you are generating a schema for a single type found in the assembly, you can use the following XML:</span></span>

```xml
<!-- This is in a file named GenerateSchemaFromType.xml. -->
<xsd xmlns='http://microsoft.com/dotnet/tools/xsd/'>
<generateSchemas>
   <type>IDItems</type>
</generateSchemas>
</xsd>
```

<span data-ttu-id="17800-220">但是若要使用上面的代码，您还必须在命令提示处提供程序集的名称。</span><span class="sxs-lookup"><span data-stu-id="17800-220">But to use preceding code, you must also supply the name of the assembly at the command prompt.</span></span> <span data-ttu-id="17800-221">在命令提示符处输入以下内容（假定 XML 文件名为 GenerateSchemaFromType.xml）：</span><span class="sxs-lookup"><span data-stu-id="17800-221">Enter the following at a command prompt (presuming the XML file is named GenerateSchemaFromType.xml):</span></span>

```console
xsd /p:GenerateSchemaFromType.xml ConsoleApplication1.exe
```

<span data-ttu-id="17800-222">必须为 `<generateSchemas>` 元素仅指定以下选项中的一个。</span><span class="sxs-lookup"><span data-stu-id="17800-222">You must specify only one of the following options for the `<generateSchemas>` element.</span></span>

|<span data-ttu-id="17800-223">元素</span><span class="sxs-lookup"><span data-stu-id="17800-223">Element</span></span>|<span data-ttu-id="17800-224">描述</span><span class="sxs-lookup"><span data-stu-id="17800-224">Description</span></span>|
|-------------|-----------------|
|<span data-ttu-id="17800-225">\<assembly></span><span class="sxs-lookup"><span data-stu-id="17800-225">\<assembly></span></span>|<span data-ttu-id="17800-226">指定将从中生成架构的程序集。</span><span class="sxs-lookup"><span data-stu-id="17800-226">Specifies an assembly to generate the schema from.</span></span>|
|<span data-ttu-id="17800-227">\<type></span><span class="sxs-lookup"><span data-stu-id="17800-227">\<type></span></span>|<span data-ttu-id="17800-228">指定程序集中找到的要为其生成架构的类型。</span><span class="sxs-lookup"><span data-stu-id="17800-228">Specifies a type found in an assembly to generate a schema for.</span></span>|
|<span data-ttu-id="17800-229">\<xml></span><span class="sxs-lookup"><span data-stu-id="17800-229">\<xml></span></span>|<span data-ttu-id="17800-230">指定要为其生成架构的 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="17800-230">Specifies an XML file to generate a schema for.</span></span>|
|<span data-ttu-id="17800-231">\<xdr></span><span class="sxs-lookup"><span data-stu-id="17800-231">\<xdr></span></span>|<span data-ttu-id="17800-232">指定要为其生成架构的 XDR 文件。</span><span class="sxs-lookup"><span data-stu-id="17800-232">Specifies an XDR file to generate a schema for.</span></span>|

<span data-ttu-id="17800-233">若要生成代码文件，请使用 `<generateClasses>` 元素。</span><span class="sxs-lookup"><span data-stu-id="17800-233">To generate a code file, use the `<generateClasses>` element.</span></span> <span data-ttu-id="17800-234">下面的示例生成一个代码文件。</span><span class="sxs-lookup"><span data-stu-id="17800-234">The following example generates a code file.</span></span> <span data-ttu-id="17800-235">请注意，另外还显示了两个特性，它们允许您为生成的文件设置编程语言和命名空间。</span><span class="sxs-lookup"><span data-stu-id="17800-235">Note that two attributes are also shown that allow you to set the programming language and namespace of the generated file.</span></span>

```xml
<xsd xmlns='http://microsoft.com/dotnet/tools/xsd/'>
<generateClasses language='VB' namespace='Microsoft.Serialization.Examples'/>
</xsd>
<!-- You must supply an .xsd file when typing in the command line.-->
<!-- For example: xsd /p:genClasses mySchema.xsd -->
```

 <span data-ttu-id="17800-236">可为 `<generateClasses>` 元素设置以下选项。</span><span class="sxs-lookup"><span data-stu-id="17800-236">Options you can set for the `<generateClasses>` element include the following.</span></span>

|<span data-ttu-id="17800-237">元素</span><span class="sxs-lookup"><span data-stu-id="17800-237">Element</span></span>|<span data-ttu-id="17800-238">描述</span><span class="sxs-lookup"><span data-stu-id="17800-238">Description</span></span>|
|-------------|-----------------|
|<span data-ttu-id="17800-239">\<element></span><span class="sxs-lookup"><span data-stu-id="17800-239">\<element></span></span>|<span data-ttu-id="17800-240">指定 .xsd 文件中要为其生成代码的元素。</span><span class="sxs-lookup"><span data-stu-id="17800-240">Specifies an element in the .xsd file to generate code for.</span></span>|
|<span data-ttu-id="17800-241">\<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="17800-241">\<schemaImporterExtensions></span></span>|<span data-ttu-id="17800-242">指定派生自 <xref:System.Xml.Serialization.Advanced.SchemaImporterExtension> 类的类型。</span><span class="sxs-lookup"><span data-stu-id="17800-242">Specifies a type derived from the <xref:System.Xml.Serialization.Advanced.SchemaImporterExtension> class.</span></span>|
|<span data-ttu-id="17800-243">\<schema></span><span class="sxs-lookup"><span data-stu-id="17800-243">\<schema></span></span>|<span data-ttu-id="17800-244">指定要为其生成代码的 XML 架构文件。</span><span class="sxs-lookup"><span data-stu-id="17800-244">Specifies a XML Schema file to generate code for.</span></span> <span data-ttu-id="17800-245">可使用多个 \<schema> 元素指定多个 XML 架构文件。</span><span class="sxs-lookup"><span data-stu-id="17800-245">Multiple XML Schema files can be specified using multiple \<schema> elements.</span></span>|

<span data-ttu-id="17800-246">下表显示也可用于 `<generateClasses>` 元素的特性。</span><span class="sxs-lookup"><span data-stu-id="17800-246">The following table shows the attributes that can also be used with the `<generateClasses>` element.</span></span>

|<span data-ttu-id="17800-247">特性</span><span class="sxs-lookup"><span data-stu-id="17800-247">Attribute</span></span>|<span data-ttu-id="17800-248">描述</span><span class="sxs-lookup"><span data-stu-id="17800-248">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="17800-249">语言</span><span class="sxs-lookup"><span data-stu-id="17800-249">language</span></span>|<span data-ttu-id="17800-250">指定要使用的编程语言。</span><span class="sxs-lookup"><span data-stu-id="17800-250">Specifies the programming language to use.</span></span> <span data-ttu-id="17800-251">从 `CS`（默认情况下为 C#）、`VB` (Visual Basic)、`JS` (JScript) 或 `VJS` (Visual J#) 中进行选择。</span><span class="sxs-lookup"><span data-stu-id="17800-251">Choose from `CS` (C#, the default), `VB` (Visual Basic), `JS` (JScript), or `VJS` (Visual J#).</span></span> <span data-ttu-id="17800-252">也可指定实现 <xref:System.CodeDom.Compiler.CodeDomProvider> 的类的完全限定名。</span><span class="sxs-lookup"><span data-stu-id="17800-252">You can also specify a fully qualified name for a class that implements <xref:System.CodeDom.Compiler.CodeDomProvider>.</span></span>|
|<span data-ttu-id="17800-253">namespace</span><span class="sxs-lookup"><span data-stu-id="17800-253">namespace</span></span>|<span data-ttu-id="17800-254">为生成的代码指定命名空间。</span><span class="sxs-lookup"><span data-stu-id="17800-254">Specifies the namespace for the generated code.</span></span> <span data-ttu-id="17800-255">命名空间必须符合 CLR 标准（例如，没有空格或反斜杠字符）。</span><span class="sxs-lookup"><span data-stu-id="17800-255">The namespace must conform to CLR standards (for example, no spaces or backslash characters).</span></span>|
|<span data-ttu-id="17800-256">选项</span><span class="sxs-lookup"><span data-stu-id="17800-256">options</span></span>|<span data-ttu-id="17800-257">以下值之一：`none`、`properties`（生成属性而不是公共字段）、`order` 或 `enableDataBinding`（请参见前面“XSD 文件选项”一节的 `/order` 和 `/enableDataBinding` 开关）。</span><span class="sxs-lookup"><span data-stu-id="17800-257">One of the following values: `none`, `properties` (generates properties instead of public fields), `order`, or `enableDataBinding` (see the `/order` and `/enableDataBinding` switches in the preceding XSD File Options section.</span></span>|

 <span data-ttu-id="17800-258">使用 `DataSet` 元素还可以控制如何生成 `<generateDataSet>` 代码。</span><span class="sxs-lookup"><span data-stu-id="17800-258">You can also control how `DataSet` code is generated by using the `<generateDataSet>` element.</span></span> <span data-ttu-id="17800-259">以下 XML 指定生成的代码使用`DataSet`结构（如<xref:System.Data.DataTable>类）为指定元素创建 Visual Basic 代码。</span><span class="sxs-lookup"><span data-stu-id="17800-259">The following XML specifies that the generated code uses `DataSet` structures (such as the <xref:System.Data.DataTable> class) to create Visual Basic code for a specified element.</span></span> <span data-ttu-id="17800-260">生成的数据集结构将支持 LINQ 查询。</span><span class="sxs-lookup"><span data-stu-id="17800-260">The generated DataSet structures will support LINQ queries.</span></span>

 ```xml
 <xsd xmlns='http://microsoft.com/dotnet/tools/xsd/'>
     <generateDataSet language='VB' namespace='Microsoft.Serialization.Examples' enableLinqDataSet='true'>
     </generateDataSet>
 </xsd>
```

<span data-ttu-id="17800-261">可为 `<generateDataSet>` 元素设置以下选项。</span><span class="sxs-lookup"><span data-stu-id="17800-261">Options you can set for the `<generateDataSet>` element include the following.</span></span>

|<span data-ttu-id="17800-262">元素</span><span class="sxs-lookup"><span data-stu-id="17800-262">Element</span></span>|<span data-ttu-id="17800-263">描述</span><span class="sxs-lookup"><span data-stu-id="17800-263">Description</span></span>|
|-------------|-----------------|
|<span data-ttu-id="17800-264">\<schema></span><span class="sxs-lookup"><span data-stu-id="17800-264">\<schema></span></span>|<span data-ttu-id="17800-265">指定要为其生成代码的 XML 架构文件。</span><span class="sxs-lookup"><span data-stu-id="17800-265">Specifies an XML Schema file to generate code for.</span></span> <span data-ttu-id="17800-266">可使用多个 \<schema> 元素指定多个 XML 架构文件。</span><span class="sxs-lookup"><span data-stu-id="17800-266">Multiple XML Schema files can be specified using multiple \<schema> elements.</span></span>|

 <span data-ttu-id="17800-267">下表显示可与 `<generateDataSet>` 元素一起使用的特性。</span><span class="sxs-lookup"><span data-stu-id="17800-267">The following table shows the attributes that can be used with the `<generateDataSet>` element.</span></span>

|<span data-ttu-id="17800-268">特性</span><span class="sxs-lookup"><span data-stu-id="17800-268">Attribute</span></span>|<span data-ttu-id="17800-269">描述</span><span class="sxs-lookup"><span data-stu-id="17800-269">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="17800-270">enableLinqDataSet</span><span class="sxs-lookup"><span data-stu-id="17800-270">enableLinqDataSet</span></span>|<span data-ttu-id="17800-271">指定可使用 LINQ to DataSet 查询的生成的数据集。</span><span class="sxs-lookup"><span data-stu-id="17800-271">Specifies that the generated DataSet can be queried against using LINQ to DataSet.</span></span> <span data-ttu-id="17800-272">默认值是 False。</span><span class="sxs-lookup"><span data-stu-id="17800-272">The default value is false.</span></span>|
|<span data-ttu-id="17800-273">语言</span><span class="sxs-lookup"><span data-stu-id="17800-273">language</span></span>|<span data-ttu-id="17800-274">指定要使用的编程语言。</span><span class="sxs-lookup"><span data-stu-id="17800-274">Specifies the programming language to use.</span></span> <span data-ttu-id="17800-275">从 `CS`（默认情况下为 C#）、`VB` (Visual Basic)、`JS` (JScript) 或 `VJS` (Visual J#) 中进行选择。</span><span class="sxs-lookup"><span data-stu-id="17800-275">Choose from `CS` (C#, the default), `VB` (Visual Basic), `JS` (JScript), or `VJS` (Visual J#).</span></span> <span data-ttu-id="17800-276">也可指定实现 <xref:System.CodeDom.Compiler.CodeDomProvider> 的类的完全限定名。</span><span class="sxs-lookup"><span data-stu-id="17800-276">You can also specify a fully qualified name for a class that implements <xref:System.CodeDom.Compiler.CodeDomProvider>.</span></span>|
|<span data-ttu-id="17800-277">namespace</span><span class="sxs-lookup"><span data-stu-id="17800-277">namespace</span></span>|<span data-ttu-id="17800-278">为生成的代码指定命名空间。</span><span class="sxs-lookup"><span data-stu-id="17800-278">Specifies the namespace for the generated code.</span></span> <span data-ttu-id="17800-279">命名空间必须符合 CLR 标准（例如，没有空格或反斜杠字符）。</span><span class="sxs-lookup"><span data-stu-id="17800-279">The namespace must conform to CLR standards (for example, no spaces or backslash characters).</span></span>|

 <span data-ttu-id="17800-280">有些特性可在顶级 `<xsd>` 元素上设置。</span><span class="sxs-lookup"><span data-stu-id="17800-280">There are attributes that you can set on the top level `<xsd>` element.</span></span> <span data-ttu-id="17800-281">这些选项可用于任何子元素（`<generateSchemas>`、`<generateClasses>` 或 `<generateDataSet>`）。</span><span class="sxs-lookup"><span data-stu-id="17800-281">These options can be used with any of the child elements (`<generateSchemas>`, `<generateClasses>` or `<generateDataSet>`).</span></span> <span data-ttu-id="17800-282">下面的 XML 代码在名为“MyOutputDirectory”的输出目录中为名为“IDItems”的元素生成代码。</span><span class="sxs-lookup"><span data-stu-id="17800-282">The following XML code generates code for an element named "IDItems" in the output directory named "MyOutputDirectory".</span></span>

```xml
<xsd xmlns='http://microsoft.com/dotnet/tools/xsd/' output='MyOutputDirectory'>
<generateClasses>
    <element>IDItems</element>
</generateClasses>
</xsd>
```

<span data-ttu-id="17800-283">下表显示也可用于 `<xsd>` 元素的特性。</span><span class="sxs-lookup"><span data-stu-id="17800-283">The following table shows the attributes that can also be used with the `<xsd>` element.</span></span>

|<span data-ttu-id="17800-284">特性</span><span class="sxs-lookup"><span data-stu-id="17800-284">Attribute</span></span>|<span data-ttu-id="17800-285">描述</span><span class="sxs-lookup"><span data-stu-id="17800-285">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="17800-286">output</span><span class="sxs-lookup"><span data-stu-id="17800-286">output</span></span>|<span data-ttu-id="17800-287">将放置生成的架构或代码文件的目录的名称。</span><span class="sxs-lookup"><span data-stu-id="17800-287">The name of a directory where the generated schema or code file will be placed.</span></span>|
|<span data-ttu-id="17800-288">nologo</span><span class="sxs-lookup"><span data-stu-id="17800-288">nologo</span></span>|<span data-ttu-id="17800-289">取消显示版权标志。</span><span class="sxs-lookup"><span data-stu-id="17800-289">Suppresses the banner.</span></span> <span data-ttu-id="17800-290">设置为 `true` 或 `false`。</span><span class="sxs-lookup"><span data-stu-id="17800-290">Set to `true` or `false`.</span></span>|
|<span data-ttu-id="17800-291">help</span><span class="sxs-lookup"><span data-stu-id="17800-291">help</span></span>|<span data-ttu-id="17800-292">显示该工具的命令语法和选项。</span><span class="sxs-lookup"><span data-stu-id="17800-292">Displays command syntax and options for the tool.</span></span> <span data-ttu-id="17800-293">设置为 `true` 或 `false`。</span><span class="sxs-lookup"><span data-stu-id="17800-293">Set to `true` or `false`.</span></span>|

## <a name="examples"></a><span data-ttu-id="17800-294">示例</span><span class="sxs-lookup"><span data-stu-id="17800-294">Examples</span></span>
 <span data-ttu-id="17800-295">下面的命令从 `myFile.xdr` 生成一个 XML 架构并将它保存到当前目录中。</span><span class="sxs-lookup"><span data-stu-id="17800-295">The following command generates an XML schema from `myFile.xdr` and saves it to the current directory.</span></span>

```console
xsd myFile.xdr
```

<span data-ttu-id="17800-296">下面的命令从 `myFile.xml` 生成一个 XML 架构并将它保存到指定目录中。</span><span class="sxs-lookup"><span data-stu-id="17800-296">The following command generates an XML schema from `myFile.xml` and saves it to the specified directory.</span></span>

```console
xsd myFile.xml /outputdir:myOutputDir
```

<span data-ttu-id="17800-297">下面的命令生成一个与 C# 语言中的指定架构相对应的数据集，并在当前目录中将其保存为 `XSDSchemaFile.cs`。</span><span class="sxs-lookup"><span data-stu-id="17800-297">The following command generates a data set that corresponds to the specified schema in the C# language and saves it as `XSDSchemaFile.cs` in the current directory.</span></span>

```console
xsd /dataset /language:CS XSDSchemaFile.xsd
```

<span data-ttu-id="17800-298">下面的命令为程序集 `myAssembly.dll` 中的所有类型生成 XML 架构，并在当前目录中将它们保存为 `schema0.xsd`。</span><span class="sxs-lookup"><span data-stu-id="17800-298">The following command generates XML schemas for all types in the assembly `myAssembly.dll` and saves them as `schema0.xsd` in the current directory.</span></span>

```console
xsd myAssembly.dll
```

## <a name="see-also"></a><span data-ttu-id="17800-299">请参阅</span><span class="sxs-lookup"><span data-stu-id="17800-299">See also</span></span>

- <xref:System.Data.DataSet>
- <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType>
- [<span data-ttu-id="17800-300">工具</span><span class="sxs-lookup"><span data-stu-id="17800-300">Tools</span></span>](../../../docs/framework/tools/index.md)
- [<span data-ttu-id="17800-301">命令提示</span><span class="sxs-lookup"><span data-stu-id="17800-301">Command Prompts</span></span>](../../../docs/framework/tools/developer-command-prompt-for-vs.md)
- [<span data-ttu-id="17800-302">LINQ to DataSet 概述</span><span class="sxs-lookup"><span data-stu-id="17800-302">LINQ to DataSet Overview</span></span>](../../../docs/framework/data/adonet/linq-to-dataset-overview.md)
- [<span data-ttu-id="17800-303">查询类型化数据集</span><span class="sxs-lookup"><span data-stu-id="17800-303">Querying Typed DataSets</span></span>](../../../docs/framework/data/adonet/querying-typed-datasets.md)
- [<span data-ttu-id="17800-304">LINQ（语言集成查询）（C#）</span><span class="sxs-lookup"><span data-stu-id="17800-304">LINQ (Language-Integrated Query) (C#)</span></span>](../../csharp/programming-guide/concepts/linq/index.md)
- [<span data-ttu-id="17800-305">LINQ（语言集成查询）（视觉基础）</span><span class="sxs-lookup"><span data-stu-id="17800-305">LINQ (Language-Integrated Query) (Visual Basic)</span></span>](../../visual-basic/programming-guide/concepts/linq/index.md)
