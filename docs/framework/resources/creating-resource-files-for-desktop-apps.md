---
title: "创建桌面应用程序的资源文件 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-bcl"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - ".resources 文件"
  - "应用程序资源, 创建文件"
  - "资源文件, .resources 文件"
  - "资源文件, 创建"
ms.assetid: 6c5ad891-66a0-4e7a-adcf-f41863ba6d8d
caps.latest.revision: 25
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 25
---
# 创建桌面应用程序的资源文件
可以将资源（例如，字符串、图像或对象数据）包含在资源文件中，以供应用程序轻松使用。  .NET Framework 提供了创建资源文件的五种方法：  
  
-   创建一个包含字符串资源的文本文件。  可以使用[资源文件生成器 \(Resgen.exe\)](../../../docs/framework/tools/resgen-exe-resource-file-generator.md) 将该文本文件转换为二进制资源 \(.resources\) 文件。  然后，可以使用语言编译器将该二进制资源文件嵌入应用程序可执行文件或应用程序库中，或者可以使用[程序集链接器 \(Al.exe\)](../../../docs/framework/tools/al-exe-assembly-linker.md) 将该二进制资源文件嵌入附属程序集中。  有关详细信息，请参见[文本文件中的资源](../../../docs/framework/resources/creating-resource-files-for-desktop-apps.md#TextFiles)部分。  
  
-   创建一个包含字符串、图像或对象数据的 XML 资源 \(.resx\) 文件。  可以使用[资源文件生成器 \(Resgen.exe\)](../../../docs/framework/tools/resgen-exe-resource-file-generator.md) 将 .resx 文件转换为二进制资源 \(.resources\) 文件。  然后，可以使用语言编译器将该二进制资源文件嵌入应用程序可执行文件或应用程序库中，或者可以使用[程序集链接器 \(Al.exe\)](../../../docs/framework/tools/al-exe-assembly-linker.md) 将该二进制资源文件嵌入附属程序集中。  有关详细信息，请参见 [.resx 文件中的资源](../../../docs/framework/resources/creating-resource-files-for-desktop-apps.md#ResxFiles)部分。  
  
-   使用 <xref:System.Resources> 命名空间中的类型以编程方式创建一个 XML 资源 \(.resx\) 文件。  可以创建一个 .resx 文件，枚举其资源并按名称检索特定资源。  有关更多信息，请参见主题[以编程方式使用 .resx 文件](../../../docs/framework/resources/working-with-resx-files-programmatically.md)。  
  
-   以编程方式创建一个二进制资源 \(.resources\) 文件。  然后，可以使用语言编译器将该文件嵌入应用程序可执行文件或应用程序库中，或者可以使用[程序集链接器 \(Al.exe\)](../../../docs/framework/tools/al-exe-assembly-linker.md) 将该文件嵌入附属程序集中。  有关详细信息，请参见[.resources 文件中的资源](../../../docs/framework/resources/creating-resource-files-for-desktop-apps.md#ResourcesFiles)部分。  
  
-   使用 Visual Studio 创建一个资源文件，并将该文件包含在您的项目中。  Visual Studio 提供了一个资源编辑器，可用于添加、删除和修改资源。  编译时，该资源文件会自动转换为一个二进制 .resources 文件，并会嵌入应用程序程序集或附属程序集中。  有关详细信息，请参阅 [Visual Studio 中的资源文件](../../../docs/framework/resources/creating-resource-files-for-desktop-apps.md#VSResFiles) 部分。  
  
<a name="TextFiles"></a>   
## 文本文件中的资源  
 文本\(.txt\)文件只能用来存储字符串资源；对于非字符串资源，请使用 .resx 文件或以编程方式来创建它们。  包含字符串资源的文本文件具有以下格式：  
  
```  
# This is an optional comment.  
name = value  
  
; This is another optional comment.  
name = value  
  
; The following supports conditional compilation if X is defined.  
#ifdef X  
name1=value1  
name2=value2  
#endif  
  
# The following supports conditional compilation if Y is undefined.  
#if !Y  
name1=value1  
name2=value2  
#endif  
  
```  
  
 资源文件.txt 和 .restext 文件的格式是相同的。  .restext 文件扩展名只是用来使得文本文件作为基于文本的资源文件是立即识别的。  
  
 字符串资源显示为 *name\/value* 对，其中 *name* 是标识资源的字符串， *value* 是在将*name* 传递到资源检索方法（例如 <xref:System.Resources.ResourceManager.GetString%2A?displayProperty=fullName>.）时返回的资源字符串。  *name*和 *value*必须用等号 \(\=\) 分隔开。  例如：  
  
```  
  
FileMenuName=File  
EditMenuName=Edit  
ViewMenuName=View  
HelpMenuName=Help  
  
```  
  
> [!CAUTION]
>  不要使用资源文件来存储密码、安全敏感信息或保密数据。  
  
 空字符串 \(即值为 <xref:System.String.Empty?displayProperty=fullName> 的资源）在文本文件中是允许的。  例如：  
  
```  
EmptyString=  
```  
  
 从 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]开始，文本文件支持与 `#ifdef` *symbol*的条件编译   `#endif` 和 `#if !`*symbol*...  `#endif`构造。  然后可以使用 `/define` 交换[资源文件生成器 \(resgen.exe\)](../../../docs/framework/tools/resgen-exe-resource-file-generator.md)来定义符号。  每个资源都需要它们自己的 `#ifdef` *symbol*…  `#endif`或者`#if !`*symbol*...  `#endif`构造。  如果使用的是 `#ifdef` 语句，并 *symbol* 已被定义，则这种关联的资源包括在 .resources 文件中；否则，它不包括在内。  如果使用的是 `#if !` 语句，并 *symbol* 没有被定义，则这种关联的资源包括在 .resources 文件中；否则，它不包括在内。  
  
 注释在文本文件中是可选的，并且注释行均以分号 \(;\) 或井号 \(\#\) 开头。  可将包含注释的行放置在文件中的任意位置。  使用[资源文件生成器 \(Resgen.exe\)](../../../docs/framework/tools/resgen-exe-resource-file-generator.md) 创建的已编译 .resources 文件中不包含注释。  
  
 文本文件中的任意空行将视为空白，并将被忽略。  
  
 下面的示例定义了分别名为 `OKButton` 和 `CancelButton` 的两个字符串资源。  
  
```  
#Define resources for buttons in the user interface.  
OKButton=OK  
CancelButton=Cancel  
```  
  
 如果 .text 文件包含 *name* 的重复匹配项，则 [资源文件生成器 \(Resgen.exe\)](../../../docs/framework/tools/resgen-exe-resource-file-generator.md)将显示一条警告并忽略第二个名称。  
  
 *value* 不能包含换行符，但您可以使用 C 语言样式的转义符（如使用 `\n` 表示新行，使用   `\t`表示制表符）。  您还可以包含反斜杠字符如果它是转义的 \(例如，“\\\\"\)。  此外，允许使用空字符串。  
  
 您应该使用 little\-endian 或 big\-endian 字节顺序的 UTF\-8 编码或 UTF\-16 编码以文本文件格式保存资源。  但是，[资源文件生成器 \(Resgen.exe\)](../../../docs/framework/tools/resgen-exe-resource-file-generator.md)（它可将 .txt 文件转换为 .resources 文件）默认情况下会将文件视为 UTF\-8。  若要让 Resgen.exe 识别使用 UTF\-16 编码的文件，必须在该文件的开头包含 Unicode 字节顺序标记 \(U\+FEFF\)。  
  
 若要将一个文本格式的资源文件嵌入 .NET Framework 程序集中，则必须使用[资源文件生成器 \(Resgen.exe\)](../../../docs/framework/tools/resgen-exe-resource-file-generator.md) 将该文件转换为二进制资源 \(.resources\) 文件。  然后，可以使用语言编译器将 .resources 文件嵌入 .NET Framework 程序集中，或者可以使用[程序集链接器 \(Al.exe\)](../../../docs/framework/tools/al-exe-assembly-linker.md) 将该文件嵌入附属程序集中。  
  
 下面的示例对一个简单的“Hello World”控制台应用程序使用一个名为 GreetingResources.txt 的文本格式的资源文件。  该文本文件定义了 `prompt` 字符串和 `greeting` 字符串，二者提示用户输入其姓名并显示一句问候语。  
  
```  
# GreetingResources.txt   
# A resource file in text format for a "Hello World" application.  
#  
# Initial prompt to the user.  
prompt=Enter your name:   
# Format string to display the result.  
greeting=Hello, {0}!  
```  
  
 使用以下命令将文本文件转换为 .resources 文件：  
  
 **resgen GreetingResources.txt**  
  
 下面的示例显示了控制台应用程序的源代码，该应用程序使用 .resources 文件向用户显示消息。  
  
 [!code-csharp[Conceptual.Resources.TextFiles#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.textfiles/cs/greeting.cs#1)]
 [!code-vb[Conceptual.Resources.TextFiles#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.textfiles/vb/greeting.vb#1)]  
  
 如果您使用的是 Visual Basic 且源代码文件名为 Greeting.vb，则以下命令将创建一个包含嵌入的 .resources 文件的可执行文件：  
  
 **vbc greeting.vb \/resource:GreetingResources.resources**  
  
 如果您使用的是 C\# 且源代码文件名为 Greeting.cs，则以下命令将创建一个包含嵌入的 .resources 文件的可执行文件：  
  
 **csc greeting.cs \/resource:GreetingResources.resources**  
  
<a name="ResxFiles"></a>   
## .resx 文件中的资源  
 与只能存储字符串资源的文本文件不同，XML 资源 \(.resx\) 文件可存储字符串、二进制数据（例如，图像、图标和音频剪辑）以及编程对象。  .resx 文件包含一个标准标头，该标头描述资源项的格式并指定用来分析数据的 XML 版本控制信息。  资源文件数据位于 XML 标头后。  每个数据项均由包含在 `data` 标记中的名称\/值对组成。  其 `name` 特性定义了资源名称，并且嵌套的 `value` 标记包含资源值。  对于字符串数据，`value` 标记包含字符串。  
  
 例如，下面的 `data` 标记定义了一个名为 `prompt` 的字符串资源，其值为“Enter your name:”。  
  
```  
<data name="prompt" xml:space="preserve">  
  <value>Enter your name:</value>  
</data>  
```  
  
> [!WARNING]
>  不要使用资源文件来存储密码、安全敏感信息或保密数据。  
  
 对于资源对象，**data** 标记包含一个 `type` 特性，该特性指示资源的数据类型。  对于包含二进制数据的对象，`data` 标记还包含一个 `mimetype` 特性，该特性指示二进制数据的 `base64` 类型。  
  
> [!NOTE]
>  所有 .resx 文件都使用二进制序列化格式化程序来生成和分析特定类型的二进制数据。  因此，如果对象的二进制序列化格式出现了不可兼容的变化，.resx 文件可能会变为无效。  
  
 下面的示例演示了 .resx 文件的一部分，该文件包含一个 <xref:System.Int32> 资源和一个位图图像。  
  
```  
  
<data name="i1" type="System.Int32, mscorlib">  
  <value>20</value>  
</data>  
  
<data name="flag" type="System.Drawing.Bitmap, System.Drawing,     
    Version=1.0.5000.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a"   
    mimetype="application/x-microsoft.net.object.bytearray.base64">  
  <value>  
    AAEAAAD/////AQAAAAAAAAAMAgAAADtTeX…  
  </value>  
</data>  
```  
  
> [!IMPORTANT]
>  由于 .resx 文件必须由预定义格式的格式良好的 XML 组成，因此，我们建议不要手动处理 .resx 文件，特别是在 .resx 文件包含字符串以外的资源时。  相反，Visual Studio 提供了一个透明接口用于创建和操作 .resx 文件；有关详细信息，请参见 [Visual Studio 中的资源文件](../../../docs/framework/resources/creating-resource-files-for-desktop-apps.md#VSResFiles)部分。  还可以通过编程方式创建和操作 .resx 文件。  有关详细信息，请参阅[以编程方式使用 .resx 文件](../../../docs/framework/resources/working-with-resx-files-programmatically.md)。  
  
<a name="ResourcesFiles"></a>   
## .resources 文件中的资源  
 可以使用 <xref:System.Resources.ResourceWriter?displayProperty=fullName> 类直接从代码中以编程方式创建二进制资源 \(.resources\) 文件。  还可以使用[资源文件生成器 \(Resgen.exe\)](../../../docs/framework/tools/resgen-exe-resource-file-generator.md) 从文本文件或 .resx 文件创建 .resources 文件。  除字符串数据外，.resources 文件还可包含二进制数据（字节数组）和对象数据。  以编程方式创建 .resources 文件需要执行以下步骤：  
  
1.  创建一个具有唯一文件名的 <xref:System.Resources.ResourceWriter> 对象。  可以通过为 <xref:System.Resources.ResourceWriter> 类构造函数指定文件名或文件流来做到这一点。  
  
2.  对于要添加到该文件的每个命名资源，调用 <xref:System.Resources.ResourceWriter.AddResource%2A?displayProperty=fullName> 方法的重载之一。  资源可以是字符串、对象或二进制数据（字节数组）集合。  
  
3.  调用 <xref:System.Resources.ResourceWriter.Close%2A?displayProperty=fullName> 方法以将资源写入该文件并关闭 <xref:System.Resources.ResourceWriter> 对象。  
  
> [!NOTE]
>  不要使用资源文件来存储密码、安全敏感信息或保密数据。  
  
 下面的示例以编程方式创建了一个名为 CarResources.resources 的 .resources 文件，该文件存储了六个字符串、一个图标和两个应用程序定义的对象（两个 `Automobile` 对象）。  请注意，该示例中定义和实例化的 `Automobile` 类标记了 <xref:System.SerializableAttribute> 特性，这使它将为二进制序列化格式化程序所保存。  
  
 [!code-csharp[Conceptual.Resources.Resources#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.resources/cs/resources1.cs#1)]
 [!code-vb[Conceptual.Resources.Resources#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.resources/vb/resources1.vb#1)]  
  
 在创建 .resources 文件后，可以通过包含语言编译器的 `/resource` 开关将该文件嵌入运行时可执行文件或库中，或者可以通过使用[程序集链接器 \(Al.exe\)](../../../docs/framework/tools/al-exe-assembly-linker.md) 将该文件嵌入附属程序集中。  
  
<a name="VSResFiles"></a>   
## Visual Studio 中的资源文件  
 在向 Visual Studio 项目中添加资源文件时，Visual Studio 会在项目目录中创建一个 .resx 文件。  Visual Studio 提供了一个资源编辑器，可用于添加字符串、图像和二进制对象。  由于编辑器设计为仅处理静态数据，因此无法使用编辑器存储编程对象；您必须以编程方式将对象数据写入 .resx 文件或 .resources 文件。  请参见 [以编程方式使用 .resx 文件](../../../docs/framework/resources/working-with-resx-files-programmatically.md) 主题和[.resources 文件中的资源](../../../docs/framework/resources/creating-resource-files-for-desktop-apps.md#ResourcesFiles) 部分来获取有关更多信息。  
  
 如果您添加的是本地化资源，则应为这些资源提供与主资源文件相同的根文件名，并且还应在文件名中指定其区域性。  例如，如果您添加一个名为 Resources.resx 的资源文件，则还可以创建名为 Resources.en\-US.resx 和 Resources.fr\-FR.resx 的资源文件以分别保留英语（美国）和法语（法国）区域性的本地化资源。  还应指定您的应用程序的默认区域性。  这是在找不到特定区域性的任何本地化资源时将使用其资源的区域性。  若要指定默认区域性，请在 Visual Studio 的解决方案资源管理器中，右击项目名称，指向“应用程序”，再单击**“程序集信息”**，然后在**“非特定语言”**列表中选择相应的语言\/区域性。  
  
 编译时，Visual Studio 首先会将项目中的 .resx 文件转换为二进制资源 \(.resources\) 文件，然后在项目的 obj 目录的子目录中存储这些文件。  Visual Studio 会将不包含本地化资源的任何资源文件嵌入项目所生成的主程序集中。  如果任何资源文件包含本地化资源，则 Visual Studio 会将它们嵌入每个本地化区域性的单独附属程序集中。  然后，它会将各个附属程序集存储在其名称与本地化区域性对应的目录中。  例如，本地化的英语（美国）资源将存储在 en\-US 子目录中的附属程序集中。  
  
## 请参阅  
 <xref:System.Resources>   
 [桌面应用程序中的资源](../../../docs/framework/resources/index.md)   
 [打包和部署资源](../../../docs/framework/resources/packaging-and-deploying-resources-in-desktop-apps.md)