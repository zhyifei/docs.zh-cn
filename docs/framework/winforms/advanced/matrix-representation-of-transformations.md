---
title: 转换的矩阵表示形式
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- composite transformations
- transformations [Windows Forms], linear
- matrices
- translations in matrix representation
- transformations [Windows Forms], composite
- vectors
- linear transformations
- transformations [Windows Forms], matrix representation of
- transformations [Windows Forms], translation
- affine transformations
ms.assetid: 0659fe00-9e0c-41c4-9118-016f2404c905
ms.openlocfilehash: 4c840d8a5abc89493bc684526ce76d34307f4ba1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33527279"
---
# <a name="matrix-representation-of-transformations"></a><span data-ttu-id="997f5-102">转换的矩阵表示形式</span><span class="sxs-lookup"><span data-stu-id="997f5-102">Matrix Representation of Transformations</span></span>
<span data-ttu-id="997f5-103">M × n 矩阵是一组按 m 行和 n 列排列的数字。</span><span class="sxs-lookup"><span data-stu-id="997f5-103">An m×n matrix is a set of numbers arranged in m rows and n columns.</span></span> <span data-ttu-id="997f5-104">下图显示几个矩阵。</span><span class="sxs-lookup"><span data-stu-id="997f5-104">The following illustration shows several matrices.</span></span>  
  
 <span data-ttu-id="997f5-105">![转换](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art04.gif "AboutGdip05_art04")</span><span class="sxs-lookup"><span data-stu-id="997f5-105">![Transformations](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art04.gif "AboutGdip05_art04")</span></span>  
  
 <span data-ttu-id="997f5-106">您可以通过添加各个元素添加相同大小的两个矩阵。</span><span class="sxs-lookup"><span data-stu-id="997f5-106">You can add two matrices of the same size by adding individual elements.</span></span> <span data-ttu-id="997f5-107">下图显示矩阵添加两个的示例。</span><span class="sxs-lookup"><span data-stu-id="997f5-107">The following illustration shows two examples of matrix addition.</span></span>  
  
 <span data-ttu-id="997f5-108">![转换](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art05.gif "AboutGdip05_art05")</span><span class="sxs-lookup"><span data-stu-id="997f5-108">![Transformations](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art05.gif "AboutGdip05_art05")</span></span>  
  
 <span data-ttu-id="997f5-109">M × n 矩阵可以乘以 n × p 矩阵，并且结果为 m × p 矩阵。</span><span class="sxs-lookup"><span data-stu-id="997f5-109">An m×n matrix can be multiplied by an n×p matrix, and the result is an m×p matrix.</span></span> <span data-ttu-id="997f5-110">中的第一个矩阵的列数必须与第二个矩阵中的行数相同。</span><span class="sxs-lookup"><span data-stu-id="997f5-110">The number of columns in the first matrix must be the same as the number of rows in the second matrix.</span></span> <span data-ttu-id="997f5-111">例如的 4 × 2 矩阵 2 的 × 3 矩阵来生成的 4 × 3 矩阵相乘。</span><span class="sxs-lookup"><span data-stu-id="997f5-111">For example, a 4×2 matrix can be multiplied by a 2×3 matrix to produce a 4×3 matrix.</span></span>  
  
 <span data-ttu-id="997f5-112">平面和行和列矩阵的中点可以看作向量。</span><span class="sxs-lookup"><span data-stu-id="997f5-112">Points in the plane and rows and columns of a matrix can be thought of as vectors.</span></span> <span data-ttu-id="997f5-113">例如，（2，5） 是一个具有两个组件，向量和 （3，7，1） 是一个具有三个组件的向量。</span><span class="sxs-lookup"><span data-stu-id="997f5-113">For example, (2, 5) is a vector with two components, and (3, 7, 1) is a vector with three components.</span></span> <span data-ttu-id="997f5-114">两个向量的点积，如下所示定义：</span><span class="sxs-lookup"><span data-stu-id="997f5-114">The dot product of two vectors is defined as follows:</span></span>  
  
 <span data-ttu-id="997f5-115">(a、 b） • (c，d) = ac + bd</span><span class="sxs-lookup"><span data-stu-id="997f5-115">(a, b) • (c, d) = ac + bd</span></span>  
  
 <span data-ttu-id="997f5-116">(a、 b、 c） • （d、 e、 f） 有 + = ad + cf</span><span class="sxs-lookup"><span data-stu-id="997f5-116">(a, b, c) • (d, e, f) = ad + be + cf</span></span>  
  
 <span data-ttu-id="997f5-117">例如，个的点积 （2、 3） 和 （5，4） 是 (2)(5) + (3)(4) = 22。</span><span class="sxs-lookup"><span data-stu-id="997f5-117">For example, the dot product of (2, 3) and (5, 4) is (2)(5) + (3)(4) = 22.</span></span> <span data-ttu-id="997f5-118">点积 （2、 5、 1） 和 （4，3，1） 是 (2)(4) + (5)(3) + (1)(1) = 24。</span><span class="sxs-lookup"><span data-stu-id="997f5-118">The dot product of (2, 5, 1) and (4, 3, 1) is (2)(4) + (5)(3) + (1)(1) = 24.</span></span> <span data-ttu-id="997f5-119">请注意两个向量的点积，是一个数字，不是另一个向量。</span><span class="sxs-lookup"><span data-stu-id="997f5-119">Note that the dot product of two vectors is a number, not another vector.</span></span> <span data-ttu-id="997f5-120">另请注意，仅当两个矢量具有相同数量的组件，你可以计算点积。</span><span class="sxs-lookup"><span data-stu-id="997f5-120">Also note that you can calculate the dot product only if the two vectors have the same number of components.</span></span>  
  
 <span data-ttu-id="997f5-121">让 A(i, j) 包含矩阵 A 中的第 i 个行和 jth 列条目。</span><span class="sxs-lookup"><span data-stu-id="997f5-121">Let A(i, j) be the entry in matrix A in the ith row and the jth column.</span></span> <span data-ttu-id="997f5-122">例如 A （3，2） 是矩阵 A 中的第三行和第二列中的输入。</span><span class="sxs-lookup"><span data-stu-id="997f5-122">For example A(3, 2) is the entry in matrix A in the 3rd row and the 2nd column.</span></span> <span data-ttu-id="997f5-123">假设 A、 B 和 C 是矩阵和 AB = c。C 的条目的计算方式如下：</span><span class="sxs-lookup"><span data-stu-id="997f5-123">Suppose A, B, and C are matrices, and AB = C. The entries of C are calculated as follows:</span></span>  
  
 <span data-ttu-id="997f5-124">C （i，j） = （第 i，A 的行） • （列 j 的 B）</span><span class="sxs-lookup"><span data-stu-id="997f5-124">C(i, j) = (row i of A) • (column j of B)</span></span>  
  
 <span data-ttu-id="997f5-125">下图显示矩阵乘法的几个的示例。</span><span class="sxs-lookup"><span data-stu-id="997f5-125">The following illustration shows several examples of matrix multiplication.</span></span>  
  
 <span data-ttu-id="997f5-126">![转换](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art06.gif "AboutGdip05_art06")</span><span class="sxs-lookup"><span data-stu-id="997f5-126">![Transformations](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art06.gif "AboutGdip05_art06")</span></span>  
  
 <span data-ttu-id="997f5-127">如果您认为 1 × 2 矩阵作为平面中的点，您可以通过将乘以 2 × 2 矩阵转换该点。</span><span class="sxs-lookup"><span data-stu-id="997f5-127">If you think of a point in a plane as a 1×2 matrix, you can transform that point by multiplying it by a 2×2 matrix.</span></span> <span data-ttu-id="997f5-128">下图显示应用于点 （2，1） 的多个转换。</span><span class="sxs-lookup"><span data-stu-id="997f5-128">The following illustration shows several transformations applied to the point (2, 1).</span></span>  
  
 <span data-ttu-id="997f5-129">![转换](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art07.gif "AboutGdip05_art07")</span><span class="sxs-lookup"><span data-stu-id="997f5-129">![Transformations](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art07.gif "AboutGdip05_art07")</span></span>  
  
 <span data-ttu-id="997f5-130">所有前面的图中所示的转换都是线性转换。</span><span class="sxs-lookup"><span data-stu-id="997f5-130">All of the transformations shown in the preceding figure are linear transformations.</span></span> <span data-ttu-id="997f5-131">某些其他转换，如转换过程中，不是线性的并且无法表示为 2 × 2 矩阵相乘。</span><span class="sxs-lookup"><span data-stu-id="997f5-131">Certain other transformations, such as translation, are not linear, and cannot be expressed as multiplication by a 2×2 matrix.</span></span> <span data-ttu-id="997f5-132">假设你想开始 （2，1） 的点旋转 90 度，将其转换 3 个单位在 x 方向，并将其 y 方向的 4 个单位。</span><span class="sxs-lookup"><span data-stu-id="997f5-132">Suppose you want to start with the point (2, 1), rotate it 90 degrees, translate it 3 units in the x direction, and translate it 4 units in the y direction.</span></span> <span data-ttu-id="997f5-133">你可以通过使用跟矩阵添加矩阵乘法完成此操作。</span><span class="sxs-lookup"><span data-stu-id="997f5-133">You can accomplish this by using a matrix multiplication followed by a matrix addition.</span></span>  
  
 <span data-ttu-id="997f5-134">![转换](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art08.gif "AboutGdip05_art08")</span><span class="sxs-lookup"><span data-stu-id="997f5-134">![Transformations](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art08.gif "AboutGdip05_art08")</span></span>  
  
 <span data-ttu-id="997f5-135">线性转换 （2 × 2 矩阵相乘） 后, 跟一个翻译 （1 × 2 矩阵的加法） 称为仿射转换。</span><span class="sxs-lookup"><span data-stu-id="997f5-135">A linear transformation (multiplication by a 2×2 matrix) followed by a translation (addition of a 1×2 matrix) is called an affine transformation.</span></span> <span data-ttu-id="997f5-136">存储仿射转换矩阵 （一个用于线性部分），一个用于转换的一对中的替代方法是在 3 × 3 矩阵中存储整个转换。</span><span class="sxs-lookup"><span data-stu-id="997f5-136">An alternative to storing an affine transformation in a pair of matrices (one for the linear part and one for the translation) is to store the entire transformation in a 3×3 matrix.</span></span> <span data-ttu-id="997f5-137">若要完成此操作，请平面中的点必须存储在与虚拟的第三坐标的 1 × 3 矩阵。</span><span class="sxs-lookup"><span data-stu-id="997f5-137">To make this work, a point in the plane must be stored in a 1×3 matrix with a dummy 3rd coordinate.</span></span> <span data-ttu-id="997f5-138">常用方法是使所有第三个坐标等于 1。</span><span class="sxs-lookup"><span data-stu-id="997f5-138">The usual technique is to make all 3rd coordinates equal to 1.</span></span> <span data-ttu-id="997f5-139">例如，由矩阵 [2 1 1] 表示点 （2，1）。</span><span class="sxs-lookup"><span data-stu-id="997f5-139">For example, the point (2, 1) is represented by the matrix [2 1 1].</span></span> <span data-ttu-id="997f5-140">下图显示仿射转换 （旋转 90 度; 转换在 x 方向 3 个单位，y 方向的 4 个单位） 表示为单个 3 × 3 矩阵相乘。</span><span class="sxs-lookup"><span data-stu-id="997f5-140">The following illustration shows an affine transformation (rotate 90 degrees; translate 3 units in the x direction, 4 units in the y direction) expressed as multiplication by a single 3×3 matrix.</span></span>  
  
 <span data-ttu-id="997f5-141">![转换](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art09.gif "AboutGdip05_art09")</span><span class="sxs-lookup"><span data-stu-id="997f5-141">![Transformations](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art09.gif "AboutGdip05_art09")</span></span>  
  
 <span data-ttu-id="997f5-142">在前面的示例中，点 （2，1） 映射到的点 （2，6）。</span><span class="sxs-lookup"><span data-stu-id="997f5-142">In the preceding example, the point (2, 1) is mapped to the point (2, 6).</span></span> <span data-ttu-id="997f5-143">请注意，3 × 3 矩阵的第三个列包含数字 0，0，1。</span><span class="sxs-lookup"><span data-stu-id="997f5-143">Note that the third column of the 3×3 matrix contains the numbers 0, 0, 1.</span></span> <span data-ttu-id="997f5-144">这将始终为仿射转换的 3 × 3 矩阵这种情况。</span><span class="sxs-lookup"><span data-stu-id="997f5-144">This will always be the case for the 3×3 matrix of an affine transformation.</span></span> <span data-ttu-id="997f5-145">重要的数字是 1 和 2 的列中的六个数字。</span><span class="sxs-lookup"><span data-stu-id="997f5-145">The important numbers are the six numbers in columns 1 and 2.</span></span> <span data-ttu-id="997f5-146">矩阵的左上角 2 × 2 部分表示线性的转换的一部分，并且第三行中的前两个条目表示平移。</span><span class="sxs-lookup"><span data-stu-id="997f5-146">The upper-left 2×2 portion of the matrix represents the linear part of the transformation, and the first two entries in the 3rd row represent the translation.</span></span>  
  
 <span data-ttu-id="997f5-147">![转换](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art10.gif "AboutGdip05_art10")</span><span class="sxs-lookup"><span data-stu-id="997f5-147">![Transformations](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art10.gif "AboutGdip05_art10")</span></span>  
  
 <span data-ttu-id="997f5-148">在[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]可以存储在仿射转换<xref:System.Drawing.Drawing2D.Matrix>对象。</span><span class="sxs-lookup"><span data-stu-id="997f5-148">In [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] you can store an affine transformation in a <xref:System.Drawing.Drawing2D.Matrix> object.</span></span> <span data-ttu-id="997f5-149">因为表示仿射转换矩阵的第三个列始终为 （0，0，1），你在前两个列中指定六个数字，在构造时<xref:System.Drawing.Drawing2D.Matrix>对象。</span><span class="sxs-lookup"><span data-stu-id="997f5-149">Because the third column of a matrix that represents an affine transformation is always (0, 0, 1), you specify only the six numbers in the first two columns when you construct a <xref:System.Drawing.Drawing2D.Matrix> object.</span></span> <span data-ttu-id="997f5-150">语句`Matrix myMatrix = new Matrix(0, 1, -1, 0, 3, 4)`构造前面的图中所示的矩阵。</span><span class="sxs-lookup"><span data-stu-id="997f5-150">The statement `Matrix myMatrix = new Matrix(0, 1, -1, 0, 3, 4)` constructs the matrix shown in the preceding figure.</span></span>  
  
## <a name="composite-transformations"></a><span data-ttu-id="997f5-151">复合转换</span><span class="sxs-lookup"><span data-stu-id="997f5-151">Composite Transformations</span></span>  
 <span data-ttu-id="997f5-152">复合转换是转换，一个跟另一个序列。</span><span class="sxs-lookup"><span data-stu-id="997f5-152">A composite transformation is a sequence of transformations, one followed by the other.</span></span> <span data-ttu-id="997f5-153">请考虑矩阵和以下列表中的转换：</span><span class="sxs-lookup"><span data-stu-id="997f5-153">Consider the matrices and transformations in the following list:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="997f5-154">矩阵 A</span><span class="sxs-lookup"><span data-stu-id="997f5-154">Matrix A</span></span>|<span data-ttu-id="997f5-155">旋转 90 度</span><span class="sxs-lookup"><span data-stu-id="997f5-155">Rotate 90 degrees</span></span>|  
|<span data-ttu-id="997f5-156">矩阵 B</span><span class="sxs-lookup"><span data-stu-id="997f5-156">Matrix B</span></span>|<span data-ttu-id="997f5-157">在 x 方向的 2 倍缩放</span><span class="sxs-lookup"><span data-stu-id="997f5-157">Scale by a factor of 2 in the x direction</span></span>|  
|<span data-ttu-id="997f5-158">矩阵 C</span><span class="sxs-lookup"><span data-stu-id="997f5-158">Matrix C</span></span>|<span data-ttu-id="997f5-159">平移 y 方向的 3 个单位</span><span class="sxs-lookup"><span data-stu-id="997f5-159">Translate 3 units in the y direction</span></span>|  
  
 <span data-ttu-id="997f5-160">如果我们从开始点 （2，1）-表示通过矩阵 [2 1 1]-和乘以 A、 B，然后 C，点 （2，1） 将进行按列出的顺序的三个转换。</span><span class="sxs-lookup"><span data-stu-id="997f5-160">If we start with the point (2, 1) — represented by the matrix [2 1 1] — and multiply by A, then B, then C, the point (2, 1) will undergo the three transformations in the order listed.</span></span>  
  
 <span data-ttu-id="997f5-161">[2 1 1]ABC = [-2 5 1]</span><span class="sxs-lookup"><span data-stu-id="997f5-161">[2 1 1]ABC = [-2 5 1]</span></span>  
  
 <span data-ttu-id="997f5-162">而是不是存储在三个单独的矩阵复合转换的三个部分，你可以乘以 A、 B 和 C 在一起以获取存储整个复合转换的单个 3 × 3 矩阵。</span><span class="sxs-lookup"><span data-stu-id="997f5-162">Rather than store the three parts of the composite transformation in three separate matrices, you can multiply A, B, and C together to get a single 3×3 matrix that stores the entire composite transformation.</span></span> <span data-ttu-id="997f5-163">假设 ABC = d。然后乘以 D 点会使相同的结果为点乘以 A、 B，然后按 c。</span><span class="sxs-lookup"><span data-stu-id="997f5-163">Suppose ABC = D. Then a point multiplied by D gives the same result as a point multiplied by A, then B, then C.</span></span>  
  
 <span data-ttu-id="997f5-164">[2 1 1]D = [-2 5 1]</span><span class="sxs-lookup"><span data-stu-id="997f5-164">[2 1 1]D = [-2 5 1]</span></span>  
  
 <span data-ttu-id="997f5-165">下图显示了矩阵 A、 B、 C 和 d。</span><span class="sxs-lookup"><span data-stu-id="997f5-165">The following illustration shows the matrices A, B, C, and D.</span></span>  
  
 <span data-ttu-id="997f5-166">![转换](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art12.gif "AboutGdip05_art12")</span><span class="sxs-lookup"><span data-stu-id="997f5-166">![Transformations](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art12.gif "AboutGdip05_art12")</span></span>  
  
 <span data-ttu-id="997f5-167">复合转换的矩阵，可以构建乘以单独的变换矩阵的事实意味着，可以在单个存储仿射转换的任何序列<xref:System.Drawing.Drawing2D.Matrix>对象。</span><span class="sxs-lookup"><span data-stu-id="997f5-167">The fact that the matrix of a composite transformation can be formed by multiplying the individual transformation matrices means that any sequence of affine transformations can be stored in a single <xref:System.Drawing.Drawing2D.Matrix> object.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="997f5-168">复合转换的顺序很重要。</span><span class="sxs-lookup"><span data-stu-id="997f5-168">The order of a composite transformation is important.</span></span> <span data-ttu-id="997f5-169">一般情况下，旋转，再缩放、 然后转换不相同与先缩放、 旋转，然后转换。</span><span class="sxs-lookup"><span data-stu-id="997f5-169">In general, rotate, then scale, then translate is not the same as scale, then rotate, then translate.</span></span> <span data-ttu-id="997f5-170">同样，矩阵乘法的顺序很重要。</span><span class="sxs-lookup"><span data-stu-id="997f5-170">Similarly, the order of matrix multiplication is important.</span></span> <span data-ttu-id="997f5-171">一般情况下，ABC 不与备份相同。</span><span class="sxs-lookup"><span data-stu-id="997f5-171">In general, ABC is not the same as BAC.</span></span>  
  
 <span data-ttu-id="997f5-172"><xref:System.Drawing.Drawing2D.Matrix>类提供用于构建复合转换的多种方法： <xref:System.Drawing.Drawing2D.Matrix.Multiply%2A>， <xref:System.Drawing.Drawing2D.Matrix.Rotate%2A>， <xref:System.Drawing.Drawing2D.Matrix.RotateAt%2A>， <xref:System.Drawing.Drawing2D.Matrix.Scale%2A>， <xref:System.Drawing.Drawing2D.Matrix.Shear%2A>，和<xref:System.Drawing.Drawing2D.Matrix.Translate%2A>。</span><span class="sxs-lookup"><span data-stu-id="997f5-172">The <xref:System.Drawing.Drawing2D.Matrix> class provides several methods for building a composite transformation: <xref:System.Drawing.Drawing2D.Matrix.Multiply%2A>, <xref:System.Drawing.Drawing2D.Matrix.Rotate%2A>, <xref:System.Drawing.Drawing2D.Matrix.RotateAt%2A>, <xref:System.Drawing.Drawing2D.Matrix.Scale%2A>, <xref:System.Drawing.Drawing2D.Matrix.Shear%2A>, and <xref:System.Drawing.Drawing2D.Matrix.Translate%2A>.</span></span> <span data-ttu-id="997f5-173">下面的示例创建一个复合转换，它首先旋转 30 度，然后按 y 方向的 2 倍缩放并会将 5 个单位在 x 方向的转换的矩阵。</span><span class="sxs-lookup"><span data-stu-id="997f5-173">The following example creates the matrix of a composite transformation that first rotates 30 degrees, then scales by a factor of 2 in the y direction, and then translates 5 units in the x direction:</span></span>  
  
 [!code-csharp[System.Drawing.CoordinateSystems#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.CoordinateSystems#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#11)]  
  
 <span data-ttu-id="997f5-174">下图显示矩阵。</span><span class="sxs-lookup"><span data-stu-id="997f5-174">The following illustration shows the matrix.</span></span>  
  
 <span data-ttu-id="997f5-175">![转换](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art13.gif "AboutGdip05_art13")</span><span class="sxs-lookup"><span data-stu-id="997f5-175">![Transformations](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art13.gif "AboutGdip05_art13")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="997f5-176">请参阅</span><span class="sxs-lookup"><span data-stu-id="997f5-176">See Also</span></span>  
 [<span data-ttu-id="997f5-177">坐标系统和转换</span><span class="sxs-lookup"><span data-stu-id="997f5-177">Coordinate Systems and Transformations</span></span>](../../../../docs/framework/winforms/advanced/coordinate-systems-and-transformations.md)  
 [<span data-ttu-id="997f5-178">在托管 GDI+ 中使用转换</span><span class="sxs-lookup"><span data-stu-id="997f5-178">Using Transformations in Managed GDI+</span></span>](../../../../docs/framework/winforms/advanced/using-transformations-in-managed-gdi.md)
