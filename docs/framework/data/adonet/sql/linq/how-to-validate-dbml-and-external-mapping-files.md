---
title: 如何：验证 DBML 和外部映射文件
ms.date: 03/30/2017
ms.assetid: d9ea37f5-0a9e-4401-8fc3-1e6fd44c49f9
ms.openlocfilehash: 42cba5b9b686f5f94d4ebf8f889461e1bab009b5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54692725"
---
# <a name="how-to-validate-dbml-and-external-mapping-files"></a><span data-ttu-id="e94ce-102">如何：验证 DBML 和外部映射文件</span><span class="sxs-lookup"><span data-stu-id="e94ce-102">How to: Validate DBML and External Mapping Files</span></span>
<span data-ttu-id="e94ce-103">您修改的外部映射文件和 .dbml 文件必须通过其各自架构定义的验证。</span><span class="sxs-lookup"><span data-stu-id="e94ce-103">External mapping files and .dbml files that you modify must be validated against their respective schema definitions.</span></span> <span data-ttu-id="e94ce-104">本主题提供了 Visual Studio 用户的步骤来实现验证过程。</span><span class="sxs-lookup"><span data-stu-id="e94ce-104">This topic provides Visual Studio users with the steps to implement the validation process.</span></span>  
  
 [!INCLUDE[note_settings_general](../../../../../../includes/note-settings-general-md.md)]  
  
### <a name="to-validate-a-dbml-or-xml-file"></a><span data-ttu-id="e94ce-105">验证 .dbml 或 XML 文件</span><span class="sxs-lookup"><span data-stu-id="e94ce-105">To validate a .dbml or XML file</span></span>  
  
1.  <span data-ttu-id="e94ce-106">在 Visual Studio**文件**菜单，依次指向**打开**，然后单击**文件**。</span><span class="sxs-lookup"><span data-stu-id="e94ce-106">On the Visual Studio **File** menu, point to **Open**, and then click **File**.</span></span>  
  
2.  <span data-ttu-id="e94ce-107">在中**打开的文件**对话框框中，单击.dbml 或你想要验证的 XML 映射文件。</span><span class="sxs-lookup"><span data-stu-id="e94ce-107">In the **Open File** dialog box, click the .dbml or XML mapping file that you want to validate.</span></span>  
  
     <span data-ttu-id="e94ce-108">在中打开文件**XML 编辑器**。</span><span class="sxs-lookup"><span data-stu-id="e94ce-108">The file opens in the **XML Editor**.</span></span>  
  
3.  <span data-ttu-id="e94ce-109">右键单击该窗口，然后依次**属性**。</span><span class="sxs-lookup"><span data-stu-id="e94ce-109">Right-click the window, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="e94ce-110">在中**属性**窗口中，单击省略号**架构**属性。</span><span class="sxs-lookup"><span data-stu-id="e94ce-110">In the **Properties** window, click the ellipsis for the **Schemas** property.</span></span>  
  
     <span data-ttu-id="e94ce-111">**XML 架构**对话框随即打开。</span><span class="sxs-lookup"><span data-stu-id="e94ce-111">The **XML Schemas** dialog box opens.</span></span>  
  
5.  <span data-ttu-id="e94ce-112">请注意符合您需要的相应架构定义。</span><span class="sxs-lookup"><span data-stu-id="e94ce-112">Note the appropriate schema definition for your purpose.</span></span>  
  
    -   <span data-ttu-id="e94ce-113">DbmlSchema.xsd 是用于验证 .dbml 文件的架构定义。</span><span class="sxs-lookup"><span data-stu-id="e94ce-113">DbmlSchema.xsd is the schema definition for validating a .dbml file.</span></span> <span data-ttu-id="e94ce-114">有关详细信息，请参阅[LINQ to SQL 中的代码生成](../../../../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md)。</span><span class="sxs-lookup"><span data-stu-id="e94ce-114">For more information, see [Code Generation in LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md).</span></span>  
  
    -   <span data-ttu-id="e94ce-115">LinqToSqlMapping.xsd 是用于验证外部 XML 映射文件的架构定义。</span><span class="sxs-lookup"><span data-stu-id="e94ce-115">LinqToSqlMapping.xsd is the schema definition for validating an external XML mapping file.</span></span> <span data-ttu-id="e94ce-116">有关详细信息，请参阅[外部映射](../../../../../../docs/framework/data/adonet/sql/linq/external-mapping.md)。</span><span class="sxs-lookup"><span data-stu-id="e94ce-116">For more information, see [External Mapping](../../../../../../docs/framework/data/adonet/sql/linq/external-mapping.md).</span></span>  
  
6.  <span data-ttu-id="e94ce-117">在中**使用**列所需的架构定义行，单击此项可打开下拉列表框中，，然后单击**使用此架构**。</span><span class="sxs-lookup"><span data-stu-id="e94ce-117">In the **Use** column of the desired schema definition row, click to open the drop-down box, and then click **Use this schema**.</span></span>  
  
     <span data-ttu-id="e94ce-118">此架构定义文件现在即与您的 DBML 或 XML 映射文件关联。</span><span class="sxs-lookup"><span data-stu-id="e94ce-118">The schema definition file is now associated with your DBML or XML mapping file.</span></span>  
  
     <span data-ttu-id="e94ce-119">请确保未选择其他架构定义。</span><span class="sxs-lookup"><span data-stu-id="e94ce-119">Make sure no other schema definitions are selected.</span></span>  
  
7.  <span data-ttu-id="e94ce-120">上**视图**菜单上，单击**错误列表**。</span><span class="sxs-lookup"><span data-stu-id="e94ce-120">On the **View** menu, click **Error List**.</span></span>  
  
     <span data-ttu-id="e94ce-121">确定是否已生成了错误、警告或消息。</span><span class="sxs-lookup"><span data-stu-id="e94ce-121">Determine whether errors, warnings, or messages have been generated.</span></span> <span data-ttu-id="e94ce-122">如果未生成，则说明此 XML 文件对此架构定义有效。</span><span class="sxs-lookup"><span data-stu-id="e94ce-122">If not, the XML file is valid against the schema definition.</span></span>  
  
## <a name="alternate-method-for-supplying-schema-definition"></a><span data-ttu-id="e94ce-123">提供架构定义的另一种方法</span><span class="sxs-lookup"><span data-stu-id="e94ce-123">Alternate Method for Supplying Schema Definition</span></span>  
 <span data-ttu-id="e94ce-124">如果出于某种原因相应的.xsd 文件未出现在**XML 架构**对话框中，您可以下载此.xsd 文件从帮助主题。</span><span class="sxs-lookup"><span data-stu-id="e94ce-124">If for some reason the appropriate .xsd file does not appear in the **XML Schemas** dialog box, you can download the .xsd file from a Help topic.</span></span> <span data-ttu-id="e94ce-125">以下步骤帮助你所需的 Visual Studio XML 编辑器中的 Unicode 格式保存下载的文件。</span><span class="sxs-lookup"><span data-stu-id="e94ce-125">The following steps help you save the downloaded file in the Unicode format required by the Visual Studio XML Editor.</span></span>  
  
#### <a name="to-copy-a-schema-definition-file-from-a-help-topic"></a><span data-ttu-id="e94ce-126">从帮助主题中复制架构定义文件</span><span class="sxs-lookup"><span data-stu-id="e94ce-126">To copy a schema definition file from a Help topic</span></span>  
  
1.  <span data-ttu-id="e94ce-127">找到包含本主题前面部分所述架构定义的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="e94ce-127">Locate the Help topic that contains the schema definition as described earlier in this topic.</span></span>  
  
    -   <span data-ttu-id="e94ce-128">对于.dbml 文件，请参阅[LINQ to SQL 中的代码生成](../../../../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md)。</span><span class="sxs-lookup"><span data-stu-id="e94ce-128">For .dbml files, see [Code Generation in LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md).</span></span>  
  
    -   <span data-ttu-id="e94ce-129">对于外部映射文件，请参阅[外部映射](../../../../../../docs/framework/data/adonet/sql/linq/external-mapping.md)。</span><span class="sxs-lookup"><span data-stu-id="e94ce-129">For external mapping files, see [External Mapping](../../../../../../docs/framework/data/adonet/sql/linq/external-mapping.md).</span></span>  
  
2.  <span data-ttu-id="e94ce-130">单击**复制代码**代码文件复制到剪贴板。</span><span class="sxs-lookup"><span data-stu-id="e94ce-130">Click **Copy Code** to copy the code file to the Clipboard.</span></span>  
  
3.  <span data-ttu-id="e94ce-131">启动记事本以创建一个新文件。</span><span class="sxs-lookup"><span data-stu-id="e94ce-131">Start Notepad to create a new file.</span></span>  
  
4.  <span data-ttu-id="e94ce-132">将剪贴板中的代码粘贴到记事本文件中。</span><span class="sxs-lookup"><span data-stu-id="e94ce-132">Paste the code from the clipboard into Notepad file.</span></span>  
  
5.  <span data-ttu-id="e94ce-133">在记事本**文件**菜单上，单击**另存为**。</span><span class="sxs-lookup"><span data-stu-id="e94ce-133">On the Notepad **File** menu, click **Save As**.</span></span>  
  
6.  <span data-ttu-id="e94ce-134">在中**编码**框中，选择**Unicode**。</span><span class="sxs-lookup"><span data-stu-id="e94ce-134">In the **Encoding** box, select **Unicode**.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="e94ce-135">这样选择可保证在此文本文件前面加上 Unicode 16 字节顺序标记 (`FFFE`)。</span><span class="sxs-lookup"><span data-stu-id="e94ce-135">This selection guarantees that the Unicode-16 byte-order marker (`FFFE`) is prepended to the text file.</span></span>  
  
7.  <span data-ttu-id="e94ce-136">在中**文件名**框中，创建具有.xsd 扩展名的文件名。</span><span class="sxs-lookup"><span data-stu-id="e94ce-136">In the **File name** box, create a file name with an .xsd extension.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e94ce-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="e94ce-137">See also</span></span>
- [<span data-ttu-id="e94ce-138">引用</span><span class="sxs-lookup"><span data-stu-id="e94ce-138">Reference</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/reference.md)
