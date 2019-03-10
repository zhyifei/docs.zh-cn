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
ms.openlocfilehash: 1f98dac8b9d14cac01e109627d40fe01c37c6954
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2019
ms.locfileid: "57720821"
---
# <a name="matrix-representation-of-transformations"></a><span data-ttu-id="8d366-102">转换的矩阵表示形式</span><span class="sxs-lookup"><span data-stu-id="8d366-102">Matrix Representation of Transformations</span></span>
<span data-ttu-id="8d366-103">M × n 矩阵是一组按 m 行和 n 列排列的数字。</span><span class="sxs-lookup"><span data-stu-id="8d366-103">An m×n matrix is a set of numbers arranged in m rows and n columns.</span></span> <span data-ttu-id="8d366-104">下图显示了几个矩阵。</span><span class="sxs-lookup"><span data-stu-id="8d366-104">The following illustration shows several matrices.</span></span>  
  
 <span data-ttu-id="8d366-105">![Transformations](./media/aboutgdip05-art04.gif "AboutGdip05_art04")</span><span class="sxs-lookup"><span data-stu-id="8d366-105">![Transformations](./media/aboutgdip05-art04.gif "AboutGdip05_art04")</span></span>  
  
 <span data-ttu-id="8d366-106">可以通过添加各个元素添加两个相同大小的矩阵。</span><span class="sxs-lookup"><span data-stu-id="8d366-106">You can add two matrices of the same size by adding individual elements.</span></span> <span data-ttu-id="8d366-107">下图显示矩阵添加两个的示例。</span><span class="sxs-lookup"><span data-stu-id="8d366-107">The following illustration shows two examples of matrix addition.</span></span>  
  
 <span data-ttu-id="8d366-108">![Transformations](./media/aboutgdip05-art05.gif "AboutGdip05_art05")</span><span class="sxs-lookup"><span data-stu-id="8d366-108">![Transformations](./media/aboutgdip05-art05.gif "AboutGdip05_art05")</span></span>  
  
 <span data-ttu-id="8d366-109">M × n 矩阵可以是 n × p 的矩阵相乘，并且结果为 m × p 矩阵。</span><span class="sxs-lookup"><span data-stu-id="8d366-109">An m×n matrix can be multiplied by an n×p matrix, and the result is an m×p matrix.</span></span> <span data-ttu-id="8d366-110">中的第一个矩阵的列数必须与第二个矩阵中的行数相同。</span><span class="sxs-lookup"><span data-stu-id="8d366-110">The number of columns in the first matrix must be the same as the number of rows in the second matrix.</span></span> <span data-ttu-id="8d366-111">例如，4 × 2 矩阵以生成的 4 × 3 矩阵 2 × 3 矩阵相乘。</span><span class="sxs-lookup"><span data-stu-id="8d366-111">For example, a 4×2 matrix can be multiplied by a 2×3 matrix to produce a 4×3 matrix.</span></span>  
  
 <span data-ttu-id="8d366-112">可以将平面行和列的矩阵中的点视为向量。</span><span class="sxs-lookup"><span data-stu-id="8d366-112">Points in the plane and rows and columns of a matrix can be thought of as vectors.</span></span> <span data-ttu-id="8d366-113">例如，（2，5） 是包含两个组件，矢量和 （3，7，1） 是一个具有三个组件的向量。</span><span class="sxs-lookup"><span data-stu-id="8d366-113">For example, (2, 5) is a vector with two components, and (3, 7, 1) is a vector with three components.</span></span> <span data-ttu-id="8d366-114">定义两个向量的点积，如下所示：</span><span class="sxs-lookup"><span data-stu-id="8d366-114">The dot product of two vectors is defined as follows:</span></span>  
  
 <span data-ttu-id="8d366-115">(a，b） • (c、 d) = ac + bd</span><span class="sxs-lookup"><span data-stu-id="8d366-115">(a, b) • (c, d) = ac + bd</span></span>  
  
 <span data-ttu-id="8d366-116">(a、 b、 c） • （d、 e、 f） = ad + 是 + cf</span><span class="sxs-lookup"><span data-stu-id="8d366-116">(a, b, c) • (d, e, f) = ad + be + cf</span></span>  
  
 <span data-ttu-id="8d366-117">例如的点积 （2，3） 和 （5，4） 是 (2)(5) + (3)(4) = 22。</span><span class="sxs-lookup"><span data-stu-id="8d366-117">For example, the dot product of (2, 3) and (5, 4) is (2)(5) + (3)(4) = 22.</span></span> <span data-ttu-id="8d366-118">（2，5，1） 的点积和 （4，3，1） 是 (2)(4) + (5)(3) + (1)(1) = 24。</span><span class="sxs-lookup"><span data-stu-id="8d366-118">The dot product of (2, 5, 1) and (4, 3, 1) is (2)(4) + (5)(3) + (1)(1) = 24.</span></span> <span data-ttu-id="8d366-119">请注意，两个向量的点积数字，而不是另一个矢量。</span><span class="sxs-lookup"><span data-stu-id="8d366-119">Note that the dot product of two vectors is a number, not another vector.</span></span> <span data-ttu-id="8d366-120">另请注意，仅当两个向量具有相同数目的组件，可以计算点积。</span><span class="sxs-lookup"><span data-stu-id="8d366-120">Also note that you can calculate the dot product only if the two vectors have the same number of components.</span></span>  
  
 <span data-ttu-id="8d366-121">让 A(i, j) 是第 i 个行和 jth 列中的一个矩阵中的条目。</span><span class="sxs-lookup"><span data-stu-id="8d366-121">Let A(i, j) be the entry in matrix A in the ith row and the jth column.</span></span> <span data-ttu-id="8d366-122">例如 A （3，2） 是第三行和第二列中的一个矩阵中的输入。</span><span class="sxs-lookup"><span data-stu-id="8d366-122">For example A(3, 2) is the entry in matrix A in the 3rd row and the 2nd column.</span></span> <span data-ttu-id="8d366-123">假设 A、 B 和 C 是矩阵和 AB = c。C 的条目进行计算，如下所示：</span><span class="sxs-lookup"><span data-stu-id="8d366-123">Suppose A, B, and C are matrices, and AB = C. The entries of C are calculated as follows:</span></span>  
  
 <span data-ttu-id="8d366-124">C （i，j） = （A 的第 i 行） • （B 的列 j）</span><span class="sxs-lookup"><span data-stu-id="8d366-124">C(i, j) = (row i of A) • (column j of B)</span></span>  
  
 <span data-ttu-id="8d366-125">下图显示了几个示例的矩阵乘法。</span><span class="sxs-lookup"><span data-stu-id="8d366-125">The following illustration shows several examples of matrix multiplication.</span></span>  
  
 <span data-ttu-id="8d366-126">![Transformations](./media/aboutgdip05-art06.gif "AboutGdip05_art06")</span><span class="sxs-lookup"><span data-stu-id="8d366-126">![Transformations](./media/aboutgdip05-art06.gif "AboutGdip05_art06")</span></span>  
  
 <span data-ttu-id="8d366-127">如果您认为的 1 × 2 矩阵作为平面中的点，你可以通过将其乘以 2 × 2 矩阵转换该点。</span><span class="sxs-lookup"><span data-stu-id="8d366-127">If you think of a point in a plane as a 1×2 matrix, you can transform that point by multiplying it by a 2×2 matrix.</span></span> <span data-ttu-id="8d366-128">下图显示了多个转换应用于点 （2，1）。</span><span class="sxs-lookup"><span data-stu-id="8d366-128">The following illustration shows several transformations applied to the point (2, 1).</span></span>  
  
 <span data-ttu-id="8d366-129">![Transformations](./media/aboutgdip05-art07.gif "AboutGdip05_art07")</span><span class="sxs-lookup"><span data-stu-id="8d366-129">![Transformations](./media/aboutgdip05-art07.gif "AboutGdip05_art07")</span></span>  
  
 <span data-ttu-id="8d366-130">所有在上图中所示的转换都是线性转换。</span><span class="sxs-lookup"><span data-stu-id="8d366-130">All of the transformations shown in the preceding figure are linear transformations.</span></span> <span data-ttu-id="8d366-131">某些其他转换，如转换时，不是线性的并且不能表示为 2 × 2 矩阵相乘。</span><span class="sxs-lookup"><span data-stu-id="8d366-131">Certain other transformations, such as translation, are not linear, and cannot be expressed as multiplication by a 2×2 matrix.</span></span> <span data-ttu-id="8d366-132">假设你想开始使用点 （2，1），将其旋转 90 度，将其转换在 x 方向的 3 个单位并将其沿 y 方向的 4 个单位。</span><span class="sxs-lookup"><span data-stu-id="8d366-132">Suppose you want to start with the point (2, 1), rotate it 90 degrees, translate it 3 units in the x direction, and translate it 4 units in the y direction.</span></span> <span data-ttu-id="8d366-133">可以使用矩阵乘法和矩阵添加来完成此操作。</span><span class="sxs-lookup"><span data-stu-id="8d366-133">You can accomplish this by using a matrix multiplication followed by a matrix addition.</span></span>  
  
 <span data-ttu-id="8d366-134">![Transformations](./media/aboutgdip05-art08.gif "AboutGdip05_art08")</span><span class="sxs-lookup"><span data-stu-id="8d366-134">![Transformations](./media/aboutgdip05-art08.gif "AboutGdip05_art08")</span></span>  
  
 <span data-ttu-id="8d366-135">线性转换 （2 × 2 矩阵相乘） 后, 跟的翻译 （1 × 2 矩阵的加法） 称为仿射转换。</span><span class="sxs-lookup"><span data-stu-id="8d366-135">A linear transformation (multiplication by a 2×2 matrix) followed by a translation (addition of a 1×2 matrix) is called an affine transformation.</span></span> <span data-ttu-id="8d366-136">存储仿射转换矩阵 （一个用于线性部分），一个用于转换的一对中的替代方法是在 3 × 3 矩阵中存储整个转换。</span><span class="sxs-lookup"><span data-stu-id="8d366-136">An alternative to storing an affine transformation in a pair of matrices (one for the linear part and one for the translation) is to store the entire transformation in a 3×3 matrix.</span></span> <span data-ttu-id="8d366-137">若要实现此目的，平面中的点必须存储在具有虚拟的第三个坐标的 1 × 3 矩阵。</span><span class="sxs-lookup"><span data-stu-id="8d366-137">To make this work, a point in the plane must be stored in a 1×3 matrix with a dummy 3rd coordinate.</span></span> <span data-ttu-id="8d366-138">通常的方法是使所有第三个坐标等于 1。</span><span class="sxs-lookup"><span data-stu-id="8d366-138">The usual technique is to make all 3rd coordinates equal to 1.</span></span> <span data-ttu-id="8d366-139">例如，由矩阵 [2 1 1] 表示点 （2，1）。</span><span class="sxs-lookup"><span data-stu-id="8d366-139">For example, the point (2, 1) is represented by the matrix [2 1 1].</span></span> <span data-ttu-id="8d366-140">下图显示了仿射转换 （旋转 90 度; 转换在 x 方向的 3 个单位，在 y 方向的 4 个单位） 表示为单个 3 × 3 矩阵相乘。</span><span class="sxs-lookup"><span data-stu-id="8d366-140">The following illustration shows an affine transformation (rotate 90 degrees; translate 3 units in the x direction, 4 units in the y direction) expressed as multiplication by a single 3×3 matrix.</span></span>  
  
 <span data-ttu-id="8d366-141">![Transformations](./media/aboutgdip05-art09.gif "AboutGdip05_art09")</span><span class="sxs-lookup"><span data-stu-id="8d366-141">![Transformations](./media/aboutgdip05-art09.gif "AboutGdip05_art09")</span></span>  
  
 <span data-ttu-id="8d366-142">在上述示例中，（2，1） 的点到点 （2，6） 映射。</span><span class="sxs-lookup"><span data-stu-id="8d366-142">In the preceding example, the point (2, 1) is mapped to the point (2, 6).</span></span> <span data-ttu-id="8d366-143">请注意，3 × 3 矩阵的第三个列包含数字 0，0，1。</span><span class="sxs-lookup"><span data-stu-id="8d366-143">Note that the third column of the 3×3 matrix contains the numbers 0, 0, 1.</span></span> <span data-ttu-id="8d366-144">此属性始终为仿射转换 3 × 3 矩阵的大小写。</span><span class="sxs-lookup"><span data-stu-id="8d366-144">This will always be the case for the 3×3 matrix of an affine transformation.</span></span> <span data-ttu-id="8d366-145">重要的数字是 1 和 2 列中的六个数字。</span><span class="sxs-lookup"><span data-stu-id="8d366-145">The important numbers are the six numbers in columns 1 and 2.</span></span> <span data-ttu-id="8d366-146">矩阵的左上方 2 × 2 部分表示的线性转换，一部分和第三行中的前两个条目表示平移。</span><span class="sxs-lookup"><span data-stu-id="8d366-146">The upper-left 2×2 portion of the matrix represents the linear part of the transformation, and the first two entries in the 3rd row represent the translation.</span></span>  
  
 <span data-ttu-id="8d366-147">![Transformations](./media/aboutgdip05-art10.gif "AboutGdip05_art10")</span><span class="sxs-lookup"><span data-stu-id="8d366-147">![Transformations](./media/aboutgdip05-art10.gif "AboutGdip05_art10")</span></span>  
  
 <span data-ttu-id="8d366-148">在中[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]可以存储在一个仿射转换<xref:System.Drawing.Drawing2D.Matrix>对象。</span><span class="sxs-lookup"><span data-stu-id="8d366-148">In [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] you can store an affine transformation in a <xref:System.Drawing.Drawing2D.Matrix> object.</span></span> <span data-ttu-id="8d366-149">因为表示仿射转换矩阵的第三个列始终为 （0，0，1） 中的前两个列中指定仅六个数字，在构造时<xref:System.Drawing.Drawing2D.Matrix>对象。</span><span class="sxs-lookup"><span data-stu-id="8d366-149">Because the third column of a matrix that represents an affine transformation is always (0, 0, 1), you specify only the six numbers in the first two columns when you construct a <xref:System.Drawing.Drawing2D.Matrix> object.</span></span> <span data-ttu-id="8d366-150">该语句`Matrix myMatrix = new Matrix(0, 1, -1, 0, 3, 4)`构造在上图中所示的矩阵。</span><span class="sxs-lookup"><span data-stu-id="8d366-150">The statement `Matrix myMatrix = new Matrix(0, 1, -1, 0, 3, 4)` constructs the matrix shown in the preceding figure.</span></span>  
  
## <a name="composite-transformations"></a><span data-ttu-id="8d366-151">复合转换</span><span class="sxs-lookup"><span data-stu-id="8d366-151">Composite Transformations</span></span>  
 <span data-ttu-id="8d366-152">复合转换是一系列转换后, 跟另一个。</span><span class="sxs-lookup"><span data-stu-id="8d366-152">A composite transformation is a sequence of transformations, one followed by the other.</span></span> <span data-ttu-id="8d366-153">请考虑矩阵和在下面的列表中的转换：</span><span class="sxs-lookup"><span data-stu-id="8d366-153">Consider the matrices and transformations in the following list:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8d366-154">矩阵 A</span><span class="sxs-lookup"><span data-stu-id="8d366-154">Matrix A</span></span>|<span data-ttu-id="8d366-155">旋转 90 度</span><span class="sxs-lookup"><span data-stu-id="8d366-155">Rotate 90 degrees</span></span>|  
|<span data-ttu-id="8d366-156">矩阵 B</span><span class="sxs-lookup"><span data-stu-id="8d366-156">Matrix B</span></span>|<span data-ttu-id="8d366-157">通过沿 x 方向的 2 倍缩放</span><span class="sxs-lookup"><span data-stu-id="8d366-157">Scale by a factor of 2 in the x direction</span></span>|  
|<span data-ttu-id="8d366-158">矩阵 C</span><span class="sxs-lookup"><span data-stu-id="8d366-158">Matrix C</span></span>|<span data-ttu-id="8d366-159">转换在 y 方向的 3 个单位</span><span class="sxs-lookup"><span data-stu-id="8d366-159">Translate 3 units in the y direction</span></span>|  
  
 <span data-ttu-id="8d366-160">如果我们使用点 （2，1）-由矩阵 [2 1 1] 表示 — 乘以 A、 B、，然后 C，（2，1） 的点将进行按所列顺序的三个转换。</span><span class="sxs-lookup"><span data-stu-id="8d366-160">If we start with the point (2, 1) — represented by the matrix [2 1 1] — and multiply by A, then B, then C, the point (2, 1) will undergo the three transformations in the order listed.</span></span>  
  
 <span data-ttu-id="8d366-161">[2 1 1]ABC = [-2 5 1]</span><span class="sxs-lookup"><span data-stu-id="8d366-161">[2 1 1]ABC = [-2 5 1]</span></span>  
  
 <span data-ttu-id="8d366-162">而是不是存储在三个单独的矩阵复合转换的三个部分，您可以乘以 A、 B 和 C 一起以获取存储整个复合转换的一个 3 × 3 矩阵。</span><span class="sxs-lookup"><span data-stu-id="8d366-162">Rather than store the three parts of the composite transformation in three separate matrices, you can multiply A, B, and C together to get a single 3×3 matrix that stores the entire composite transformation.</span></span> <span data-ttu-id="8d366-163">假设 ABC = d。然后，乘以 D 的点提供相同的结果为点乘以 A、 B，然后按 c。</span><span class="sxs-lookup"><span data-stu-id="8d366-163">Suppose ABC = D. Then a point multiplied by D gives the same result as a point multiplied by A, then B, then C.</span></span>  
  
 <span data-ttu-id="8d366-164">[2 1 1]D = [-2 5 1]</span><span class="sxs-lookup"><span data-stu-id="8d366-164">[2 1 1]D = [-2 5 1]</span></span>  
  
 <span data-ttu-id="8d366-165">下图显示了矩阵 A、 B、 C 和 d。</span><span class="sxs-lookup"><span data-stu-id="8d366-165">The following illustration shows the matrices A, B, C, and D.</span></span>  
  
 <span data-ttu-id="8d366-166">![Transformations](./media/aboutgdip05-art12.gif "AboutGdip05_art12")</span><span class="sxs-lookup"><span data-stu-id="8d366-166">![Transformations](./media/aboutgdip05-art12.gif "AboutGdip05_art12")</span></span>  
  
 <span data-ttu-id="8d366-167">复合转换的矩阵，可以通过将单独的变换矩阵相乘格式正确的事实意味着仿射转换任何序列可以存储在单个<xref:System.Drawing.Drawing2D.Matrix>对象。</span><span class="sxs-lookup"><span data-stu-id="8d366-167">The fact that the matrix of a composite transformation can be formed by multiplying the individual transformation matrices means that any sequence of affine transformations can be stored in a single <xref:System.Drawing.Drawing2D.Matrix> object.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="8d366-168">复合转换的顺序非常重要。</span><span class="sxs-lookup"><span data-stu-id="8d366-168">The order of a composite transformation is important.</span></span> <span data-ttu-id="8d366-169">一般情况下，旋转，然后扩展，然后转换是不相同的小数位数为然后旋转，然后转换。</span><span class="sxs-lookup"><span data-stu-id="8d366-169">In general, rotate, then scale, then translate is not the same as scale, then rotate, then translate.</span></span> <span data-ttu-id="8d366-170">同样，矩阵乘法的顺序非常重要。</span><span class="sxs-lookup"><span data-stu-id="8d366-170">Similarly, the order of matrix multiplication is important.</span></span> <span data-ttu-id="8d366-171">一般情况下，ABC 不与备份相同。</span><span class="sxs-lookup"><span data-stu-id="8d366-171">In general, ABC is not the same as BAC.</span></span>  
  
 <span data-ttu-id="8d366-172"><xref:System.Drawing.Drawing2D.Matrix>类提供用于构建复合转换的多种方法： <xref:System.Drawing.Drawing2D.Matrix.Multiply%2A>， <xref:System.Drawing.Drawing2D.Matrix.Rotate%2A>， <xref:System.Drawing.Drawing2D.Matrix.RotateAt%2A>， <xref:System.Drawing.Drawing2D.Matrix.Scale%2A>， <xref:System.Drawing.Drawing2D.Matrix.Shear%2A>，和<xref:System.Drawing.Drawing2D.Matrix.Translate%2A>。</span><span class="sxs-lookup"><span data-stu-id="8d366-172">The <xref:System.Drawing.Drawing2D.Matrix> class provides several methods for building a composite transformation: <xref:System.Drawing.Drawing2D.Matrix.Multiply%2A>, <xref:System.Drawing.Drawing2D.Matrix.Rotate%2A>, <xref:System.Drawing.Drawing2D.Matrix.RotateAt%2A>, <xref:System.Drawing.Drawing2D.Matrix.Scale%2A>, <xref:System.Drawing.Drawing2D.Matrix.Shear%2A>, and <xref:System.Drawing.Drawing2D.Matrix.Translate%2A>.</span></span> <span data-ttu-id="8d366-173">下面的示例创建一个复合转换，它先旋转 30 度，然后按 2 在 y 方向中的因子缩放，然后会在 x 方向的 5 个单位将转换的矩阵。</span><span class="sxs-lookup"><span data-stu-id="8d366-173">The following example creates the matrix of a composite transformation that first rotates 30 degrees, then scales by a factor of 2 in the y direction, and then translates 5 units in the x direction:</span></span>  
  
 [!code-csharp[System.Drawing.CoordinateSystems#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.CoordinateSystems#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#11)]  
  
 <span data-ttu-id="8d366-174">下图显示了矩阵。</span><span class="sxs-lookup"><span data-stu-id="8d366-174">The following illustration shows the matrix.</span></span>  
  
 <span data-ttu-id="8d366-175">![Transformations](./media/aboutgdip05-art13.gif "AboutGdip05_art13")</span><span class="sxs-lookup"><span data-stu-id="8d366-175">![Transformations](./media/aboutgdip05-art13.gif "AboutGdip05_art13")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d366-176">请参阅</span><span class="sxs-lookup"><span data-stu-id="8d366-176">See also</span></span>
- [<span data-ttu-id="8d366-177">坐标系统和转换</span><span class="sxs-lookup"><span data-stu-id="8d366-177">Coordinate Systems and Transformations</span></span>](coordinate-systems-and-transformations.md)
- [<span data-ttu-id="8d366-178">在托管 GDI+ 中使用转换</span><span class="sxs-lookup"><span data-stu-id="8d366-178">Using Transformations in Managed GDI+</span></span>](using-transformations-in-managed-gdi.md)
