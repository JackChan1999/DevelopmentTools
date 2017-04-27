在 Android Studio 的布局编辑器中，您可以通过将小部件拖动到视觉设计编辑器来快速构建布局，无需手动编写布局 XML。此编辑器可在各种 Android 设备和版本中预览布局，并且您可以动态地调整布局大小以确保它可以很好地适应不同屏幕尺寸。布局编辑器在使用 `ConstraintLayout` 构建新布局时尤为强大，ConstraintLayout 是支持库中提供的布局管理器，它与 Android 2.3（API 级别 9）及更高版本兼容。

本页概述布局编辑器的界面和功能。如需了解有关如何使用 `ConstraintLayout` 构建布局的更多信息，请参阅[使用 ConstraintLayout 构建自适应 UI](https://developer.android.google.cn/training/constraint-layout/index.html)。

## 1. 编辑器简介

当您打开 XML 布局文件时将显示布局编辑器。与图 1 中数字相对应的编辑器区域如下：

1. **调色板**：提供小部件和布局的列表，您可以将它们拖动到编辑器内的布局中。
2. **组件****树**：显示布局的视图层次结构。在此处点击某个项目将看到它在编辑器中被选中。
3. **工具栏**：提供在编辑器中配置布局外观和编辑布局属性的按钮。
4. **设计编辑器**：以设计视图和蓝图视图相结合的方式显示布局。
5. **属性**：针对当前选择的视图提供属性控件。

**图 1.** 显示 **Design** 编辑器的布局编辑器

当您打开 XML 布局文件时，系统默认打开 **Design** 编辑器（如图 1 所示）。若想在 **Text** 编辑器中编辑 XML，则点击窗口底部的 **Text** 标签。在 **Text** 编辑器中时，通过点击窗口右侧的 **Preview** ![img](https://developer.android.google.cn/studio/images/buttons/window-preview.png)，您还可以查看 **Palette**、**Component Tree** 和 **Design** 编辑器（如图 2 所示）。不过，**Text** 编辑器不提供 **Properties** 窗口。

**提示**：通过按 Control+Shift+向右/向左箭头，您可以在 **Design** 和 **Text** 编辑器之间进行切换。

**图 2.** 打开 **Preview** 窗口的 **Text** 编辑器

### 更改预览外观

**Design** 编辑器顶行的按钮让您可以在编辑器中配置布局的外观。也可在 **Text** 编辑器的 **Preview** 窗口中打开此工具栏。

**图 3.** 布局编辑器工具栏中用于配置布局外观的按钮

与图 3 中数字相对应的按钮如下：

1. **Design and blueprint**：用于选择在编辑器中查看布局的方式。**Design** ![img](https://developer.android.google.cn/studio/images/buttons/layout-editor-design.png) 视图显示布局的彩色预览，而 **Blueprint** ![img](https://developer.android.google.cn/studio/images/buttons/layout-editor-blueprint.png) 视图仅显示每个视图的轮廓。或者，您可以并排查看 **Design + Blueprint** ![img](https://developer.android.google.cn/studio/images/buttons/layout-editor-design-blueprint.png)。**提示**：您可以通过按 B 在这些视图之间进行切换。
2. **Screen orientation**：用于在横屏和竖屏方向之间旋转设备。
3. **Device type and size**：用于选择设备类型（手机/平板电脑、Android TV 或 Android Wear）和屏幕配置（尺寸和密度）。您可以从多个预配置的设备类型和您自己的 AVD 定义中进行选择，或从列表中选择 **Add Device Definition** 新建 AVD 定义。**提示**：您可以通过拖动布局的右下角来调整设备尺寸。
4. **API version**：用于选择要在上面预览布局的 Android 版本。
5. **应用主题背景**：用于选择将应用到预览的 UI 主题背景。**注**：此按钮仅对支持的布局样式有效；因此，此列表中的许多主题背景会导致错误。
6. **Language**：用于选择显示 UI 字符串的语言。此列表仅显示字符串资源中可用的语言。如果您要编辑译文，请从下拉菜单中点击 **Edit Translations**（请参阅[使用 Translations Editor 对 UI 进行本地化](https://developer.android.google.cn/studio/write/translations-editor.html)）。
7. **Layout Variants**：用于切换到此文件的一个备用布局，或创建一个新布局（请参阅下文的[创建布局变体](https://developer.android.google.cn/studio/write/create-variant)）。

**注**：这些配置对应用的代码或清单没有任何影响（除非您选择从 **Layout Variants** 添加新的布局文件）；它们仅影响布局预览。

## 2. 创建新布局

为应用添加新布局时，首先在项目的默认 `layout/` 目录中创建一个布局文件，以便它适用于所有设备配置。在拥有默认布局后，您可以针对特定设备配置（如超大屏幕）创建该布局的变体—如果您想这么做，请跳到[创建布局变体](https://developer.android.google.cn/studio/write/create-variant)。

可通过几种不同的方式创建新布局，具体取决于您的 **Project **窗口视图，但以下步骤可从任意视图中执行。

1. 在 **Project **窗口中，点击您要在其中添加布局的模块（如 **app**）。
2. 在主菜单中，选择 **File > New > XML > Layout XML File**。
3. 在显示的对话框中，输入文件的名称、根布局标记以及布局所属的源集。然后点击 **Finish**。

**图 4.** 添加新布局 XML 文件的对话框

下面是用于创建新布局文件的其他几种方式（尽管显示的对话框各不相同）：

- 如果您已在 **Project **窗口中选择 **Project **视图：打开您的应用模块的 **res **目录，右键点击您想要向其添加布局的布局目录，然后点击 **New > Layout resource file**。
- 如果您已在 **Project **窗口中选择 **Android **视图：右键点击 **layout **文件夹，然后选择 **New > Layout resource file**。

### 创建布局变体

如果您已有布局，并想要创建备用版本以针对不同屏幕尺寸或屏幕方向优化布局，则执行以下步骤：

1. 打开原始布局文件，并确保您查看的是 **Design** 编辑器（点击窗口底部的 **Design** 标签）。
2. 在工具栏中点击 **Layout Variants**![img](https://developer.android.google.cn/studio/images/buttons/layout-editor-variants.png)。在下拉列表中，点击建议的变体（如 **Create Landscape Variant**）并完成创建，或点击 **Create Other** 并继续执行下一步。
3. 在显示的对话框中，您只需为目录名称定义资源限制符。您可以在 **Directory name** 中输入资源限制符，或从 **Available qualifiers** 列表中选择一个，然后点击 **Add** ![img](https://developer.android.google.cn/studio/images/buttons/add-arrows.png)。
4. 在添加所有限定符后，点击 **OK**。

如果您有相同布局的多个变体，当您点击 **Layout Variants** ![img](https://developer.android.google.cn/studio/images/buttons/layout-editor-variants.png)时，您可以轻松地通过显示的列表在它们之间进行切换。

如需了解有关如何为不同屏幕创建布局的详细信息，请阅读[支持不同屏幕尺寸](https://developer.android.google.cn/training/multiscreen/screensizes.html)。

### 将布局转换为 ConstraintLayout

`ConstraintLayout` 是约束布局库中提供的一个视图组，其包含在 Android Studio 2.2 及更高版本中。它是随布局编辑器一起从头开始构建的，因此，所有功能均可通过 Design 编辑器访问，您无需手动编辑 XML。ConstraintLayout 最出色之处是基于约束的布局系统，让您无需嵌套任何视图组即可构建大多数布局。

为提升布局性能，您应将较早的布局转换为 `ConstraintLayout`。Android Studio 提供内置转换器以帮助您执行此操作：

1. 在 Android Studio 中打开现有布局并点击编辑器窗口底部的 **Design** 标签。
2. 在 **Component Tree** 窗口中，右键点击布局，然后点击 **Convert layout to ConstraintLayout**。

如需了解有关如何使用 `ConstraintLayout` 构建布局的更多信息，请参阅[使用 ConstraintLayout 构建自适应 UI](https://developer.android.google.cn/training/constraint-layout/index.html)。

## 3. 将视图添加到布局

为应用构建布局需要了解[布局基础知识](https://developer.android.google.cn/guide/topics/ui/declaring-layout.html)，但 Android Studio 省去了许多直接在 XML 文件中进行的复杂工作。通过将小部件拖动到 **Design** 编辑器，并在 **Properties** ![img](https://developer.android.google.cn/studio/images/buttons/window-properties.png)窗口中优化布局属性，布局编辑器可帮助您完成许多工作。

开始构建布局时，只需将视图从 **Palette** 窗格拖动到 **Design** 编辑器。将视图置于布局中时，编辑器会根据您放置视图的布局类型指示视图与布局其余部分的关系。

例如，视频 1 显示如何将 `TextView` 拖动到 `ConstraintLayout` 来创建针对上述 `TextView` 的“位于下方”和“向左对齐”的约束（已启用 [Autoconnect](https://developer.android.google.cn/training/constraint-layout/index.html#autoconnect-infer)）。****

**视频 1.**当您将视图拖动到编辑器中时，布局编辑器可为您的视图添加约束。

将视图拖动到 `ConstraintLayout` 以外的布局时，根据该布局可用的布局属性，布局编辑器的响应方式会有所不同。

在布局中检测到的任何错误均统计在工具栏中。如需查看它们，请点击 **Show Warnings and Errors** ![img](https://developer.android.google.cn/studio/images/buttons/layout-editor-errors.png)。

**Design 编辑器中的外观仅供预览**。尽管在 **Design** 编辑器中编辑布局很难获得准确的外观，但您应在模拟器或真实设备上运行您的应用以验证结果。

如需了解有关 Android 的 View API 构建布局的方式的更多信息，请参阅[布局基础知识](https://developer.android.google.cn/guide/topics/ui/declaring-layout.html)。如需获取使用 `ConstraintLayout` 的指南，请参阅[使用 ConstraintLayout 构建自适应 UI](https://developer.android.google.cn/training/constraint-layout/index.html)。

### 编辑视图属性

**图 5.** **Properties** 窗口

您可以从 **Properties** ![img](https://developer.android.google.cn/studio/images/buttons/window-properties.png) 窗口（在布局编辑器的右侧）中编辑视图属性，而无需在 XML 中编辑。此窗口仅在打开 **Design** 编辑器时可用，因此，请确保您已选择窗口底部的 **Design** 标签。

在编辑器中选择要查看的视图并编辑该视图的常用属性。如果您需要访问该视图的更多属性，请点击 **View all properties** ![img](https://developer.android.google.cn/studio/images/buttons/layout-editor-all-properties.png)。

如果选择的视图是 `ConstraintLayout` 的子项，则“Properties”窗口在顶部提供一个带有多个控件的视图检查器，如图 7 所示。如需有关 `ConstraintLayout` 中视图属性控件的更多信息，请参阅[使用 Constraint Layout 构建自适应 UI](https://developer.android.google.cn/training/constraint-layout/index.html)。

![](https://developer.android.google.cn/studio/images/write/layout-editor-properties_2-2_2x.png)