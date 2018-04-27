---
title: 如何：向 TreeView 或 ListView 控件添加自定义信息（Windows 窗体）
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- ListItem
helpviewer_keywords:
- examples [Windows Forms], TreeView control
- examples [Windows Forms], ListView control
- ListView control [Windows Forms], adding custom information
- TreeView control [Windows Forms], adding custom information
ms.assetid: 68be11de-1d5b-430e-901f-cfbe48d14b19
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 8c7d8b881b3aa79122134deda7f5d95a98a68461
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-add-custom-information-to-a-treeview-or-listview-control-windows-forms"></a><span data-ttu-id="c5add-102">如何：向 TreeView 或 ListView 控件添加自定义信息（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="c5add-102">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>
<span data-ttu-id="c5add-103">你可以在 Windows 窗体中创建派生的节点<xref:System.Windows.Forms.TreeView>控件或中的派生的项<xref:System.Windows.Forms.ListView>控件。</span><span class="sxs-lookup"><span data-stu-id="c5add-103">You can create a derived node in a Windows Forms <xref:System.Windows.Forms.TreeView> control or a derived item in a <xref:System.Windows.Forms.ListView> control.</span></span> <span data-ttu-id="c5add-104">通过派生可添加任何所需字段，以及添加处理这些字段的自定义方法和构造函数。</span><span class="sxs-lookup"><span data-stu-id="c5add-104">Derivation allows you to add any fields you require, as well as custom methods and constructors for handling them.</span></span> <span data-ttu-id="c5add-105">此功能的用途之一是将 Customer 对象附加到每个树节点或列表项。</span><span class="sxs-lookup"><span data-stu-id="c5add-105">One use of this feature is to attach a Customer object to each tree node or list item.</span></span> <span data-ttu-id="c5add-106">此处的示例适用于<xref:System.Windows.Forms.TreeView>控件，但相同的方法可以用于<xref:System.Windows.Forms.ListView>控件。</span><span class="sxs-lookup"><span data-stu-id="c5add-106">The examples here are for a <xref:System.Windows.Forms.TreeView> control, but the same approach can be used for a <xref:System.Windows.Forms.ListView> control.</span></span>  
  
### <a name="to-derive-a-tree-node"></a><span data-ttu-id="c5add-107">派生树节点</span><span class="sxs-lookup"><span data-stu-id="c5add-107">To derive a tree node</span></span>  
  
-   <span data-ttu-id="c5add-108">创建一个新的节点类，派生自<xref:System.Windows.Forms.TreeNode>类，该类具有要记录的文件路径的自定义字段。</span><span class="sxs-lookup"><span data-stu-id="c5add-108">Create a new node class, derived from the <xref:System.Windows.Forms.TreeNode> class, which has a custom field to record a file path.</span></span>  
  
    ```vb  
    Class myTreeNode  
       Inherits TreeNode  
  
       Public FilePath As String  
  
       Sub New(ByVal fp As String)  
          MyBase.New()  
          FilePath = fp  
          Me.Text = fp.Substring(fp.LastIndexOf("\"))  
       End Sub  
    End Class  
    ```  
  
    ```csharp  
    class myTreeNode : TreeNode  
    {  
       public string FilePath;  
  
       public myTreeNode(string fp)  
       {  
          FilePath = fp;  
          this.Text = fp.Substring(fp.LastIndexOf("\\"));  
       }  
    }  
    ```  
  
    ```cpp  
    ref class myTreeNode : public TreeNode  
    {  
    public:  
       System::String ^ FilePath;  
  
       myTreeNode(System::String ^ fp)  
       {  
          FilePath = fp;  
          this->Text = fp->Substring(fp->LastIndexOf("\\"));  
       }  
    };  
    ```  
  
### <a name="to-use-a-derived-tree-node"></a><span data-ttu-id="c5add-109">使用派生的树节点</span><span class="sxs-lookup"><span data-stu-id="c5add-109">To use a derived tree node</span></span>  
  
1.  <span data-ttu-id="c5add-110">新的派生树节点可用作函数调用的参数。</span><span class="sxs-lookup"><span data-stu-id="c5add-110">You can use the new derived tree node as a parameter to function calls.</span></span>  
  
     <span data-ttu-id="c5add-111">在下例中，为文本文件位置设置的路径是 My Documents 文件夹。</span><span class="sxs-lookup"><span data-stu-id="c5add-111">In the example below, the path set for the location of the text file is the My Documents folder.</span></span> <span data-ttu-id="c5add-112">这样做是出于一个假定，即假定大多数运行 Windows 操作系统的计算机都包含此目录。</span><span class="sxs-lookup"><span data-stu-id="c5add-112">This is done because you can assume that most computers running the Windows operating system will include this directory.</span></span> <span data-ttu-id="c5add-113">这还使得具有最低系统访问级别的用户能够安全运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="c5add-113">This also allows users with minimal system access levels to safely run the application.</span></span>  
  
    ```vb  
    ' You should replace the bold text file   
    ' in the sample below with a text file of your own choosing.  
    TreeView1.Nodes.Add(New myTreeNode (System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       & "\ TextFile.txt ") )  
    ```  
  
    ```csharp  
    // You should replace the bold text file   
    // in the sample below with a text file of your own choosing.  
    // Note the escape character used (@) when specifying the path.  
    treeView1.Nodes.Add(new myTreeNode (System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       + @"\TextFile.txt") );  
    ```  
  
    ```cpp  
    // You should replace the bold text file   
    // in the sample below with a text file of your own choosing.  
    treeView1->Nodes->Add(new myTreeNode(String::Concat(  
       System::Environment::GetFolderPath  
       (System::Environment::SpecialFolder::Personal),  
       "\\TextFile.txt")));  
    ```  
  
2.  <span data-ttu-id="c5add-114">如果传递的树节点和类型化为<xref:System.Windows.Forms.TreeNode>类，则将需要强制转换为派生类。</span><span class="sxs-lookup"><span data-stu-id="c5add-114">If you are passed the tree node and it is typed as a <xref:System.Windows.Forms.TreeNode> class, then you will need to cast to your derived class.</span></span> <span data-ttu-id="c5add-115">强制转换是从一种对象类型到另一种对象类型的显式转换。</span><span class="sxs-lookup"><span data-stu-id="c5add-115">Casting is an explicit conversion from one type of object to another.</span></span> <span data-ttu-id="c5add-116">有关强制转换的详细信息，请参阅[隐式和显式转换](~/docs/visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)(Visual Basic 中)， [（) 运算符](~/docs/csharp/language-reference/operators/invocation-operator.md)(Visual C# 中)，或[强制转换运算符: （)](/cpp/cpp/cast-operator-parens) ([!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)])。</span><span class="sxs-lookup"><span data-stu-id="c5add-116">For more information on casting, see [Implicit and Explicit Conversions](~/docs/visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md) (Visual Basic), [() Operator](~/docs/csharp/language-reference/operators/invocation-operator.md) (Visual C#), or [Cast Operator: ()](/cpp/cpp/cast-operator-parens) ([!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]).</span></span>  
  
    ```vb  
    Public Sub TreeView1_AfterSelect(ByVal sender As Object, ByVal e As System.Windows.Forms.TreeViewEventArgs) Handles TreeView1.AfterSelect  
       Dim mynode As myTreeNode  
       mynode = CType(e.node, myTreeNode)  
       MessageBox.Show("Node selected is " & mynode.filepath)  
    End Sub  
    ```  
  
    ```csharp  
    protected void treeView1_AfterSelect (object sender,  
    System.Windows.Forms.TreeViewEventArgs e)  
    {  
       myTreeNode myNode = (myTreeNode)e.Node;  
       MessageBox.Show("Node selected is " + myNode.FilePath);  
    }  
    ```  
  
    ```cpp  
    private:  
       System::Void treeView1_AfterSelect(System::Object ^  sender,  
          System::Windows::Forms::TreeViewEventArgs ^  e)  
       {  
          myTreeNode ^ myNode = safe_cast<myTreeNode^>(e->Node);  
          MessageBox::Show(String::Concat("Node selected is ",   
             myNode->FilePath));  
       }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="c5add-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="c5add-117">See Also</span></span>  
 [<span data-ttu-id="c5add-118">TreeView 控件</span><span class="sxs-lookup"><span data-stu-id="c5add-118">TreeView Control</span></span>](../../../../docs/framework/winforms/controls/treeview-control-windows-forms.md)  
 [<span data-ttu-id="c5add-119">ListView 控件</span><span class="sxs-lookup"><span data-stu-id="c5add-119">ListView Control</span></span>](../../../../docs/framework/winforms/controls/listview-control-windows-forms.md)
