:github_url: hide

.. DO NOT EDIT THIS FILE!!!
.. Generated automatically from Godot engine sources.
.. Generator: https://github.com/godotengine/godot/tree/master/doc/tools/make_rst.py.
.. XML source: https://github.com/godotengine/godot/tree/master/modules/openxr/doc_classes/OpenXRCompositionLayer.xml.

.. _class_OpenXRCompositionLayer:

OpenXRCompositionLayer
======================

**实验性：** This class may be changed or removed in future versions.

**继承：** :ref:`Node3D<class_Node3D>` **<** :ref:`Node<class_Node>` **<** :ref:`Object<class_Object>`

**派生：** :ref:`OpenXRCompositionLayerCylinder<class_OpenXRCompositionLayerCylinder>`, :ref:`OpenXRCompositionLayerEquirect<class_OpenXRCompositionLayerEquirect>`, :ref:`OpenXRCompositionLayerQuad<class_OpenXRCompositionLayerQuad>`

所有 OpenXR 合成层节点的父类。

.. rst-class:: classref-introduction-group

描述
----

合成层允许 XR 合成器通过保留其质量的特殊投影，从而在头戴式设备内显示 2D 视口。这样可以在保持图层的原始分辨率的同时，渲染清晰的文本。

\ **注意：**\ 如果 OpenXR 运行时不支持给定的合成层类型，则可以使用 :ref:`ViewportTexture<class_ViewportTexture>` 生成后备网格，以模拟合成层。

.. rst-class:: classref-reftable-group

属性
----

.. table::
   :widths: auto

   +---------------------------------------+-----------------------------------------------------------------------------------+-----------+
   | :ref:`bool<class_bool>`               | :ref:`alpha_blend<class_OpenXRCompositionLayer_property_alpha_blend>`             | ``false`` |
   +---------------------------------------+-----------------------------------------------------------------------------------+-----------+
   | :ref:`bool<class_bool>`               | :ref:`enable_hole_punch<class_OpenXRCompositionLayer_property_enable_hole_punch>` | ``false`` |
   +---------------------------------------+-----------------------------------------------------------------------------------+-----------+
   | :ref:`SubViewport<class_SubViewport>` | :ref:`layer_viewport<class_OpenXRCompositionLayer_property_layer_viewport>`       |           |
   +---------------------------------------+-----------------------------------------------------------------------------------+-----------+
   | :ref:`int<class_int>`                 | :ref:`sort_order<class_OpenXRCompositionLayer_property_sort_order>`               | ``1``     |
   +---------------------------------------+-----------------------------------------------------------------------------------+-----------+

.. rst-class:: classref-reftable-group

方法
----

.. table::
   :widths: auto

   +-------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | :ref:`Vector2<class_Vector2>` | :ref:`intersects_ray<class_OpenXRCompositionLayer_method_intersects_ray>`\ (\ origin\: :ref:`Vector3<class_Vector3>`, direction\: :ref:`Vector3<class_Vector3>`\ ) |const| |
   +-------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | :ref:`bool<class_bool>`       | :ref:`is_natively_supported<class_OpenXRCompositionLayer_method_is_natively_supported>`\ (\ ) |const|                                                                      |
   +-------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

.. rst-class:: classref-section-separator

----

.. rst-class:: classref-descriptions-group

属性说明
--------

.. _class_OpenXRCompositionLayer_property_alpha_blend:

.. rst-class:: classref-property

:ref:`bool<class_bool>` **alpha_blend** = ``false`` :ref:`🔗<class_OpenXRCompositionLayer_property_alpha_blend>`

.. rst-class:: classref-property-setget

- |void| **set_alpha_blend**\ (\ value\: :ref:`bool<class_bool>`\ )
- :ref:`bool<class_bool>` **get_alpha_blend**\ (\ )

启用使用其 alpha 通道混合图层的功能。

可以与 :ref:`Viewport.transparent_bg<class_Viewport_property_transparent_bg>` 结合使用，以便为图层提供透明背景。

.. rst-class:: classref-item-separator

----

.. _class_OpenXRCompositionLayer_property_enable_hole_punch:

.. rst-class:: classref-property

:ref:`bool<class_bool>` **enable_hole_punch** = ``false`` :ref:`🔗<class_OpenXRCompositionLayer_property_enable_hole_punch>`

.. rst-class:: classref-property-setget

- |void| **set_enable_hole_punch**\ (\ value\: :ref:`bool<class_bool>`\ )
- :ref:`bool<class_bool>` **get_enable_hole_punch**\ (\ )

启用一种称为“打孔”的技术，该技术允许将合成层置于主投影层后面（即将 :ref:`sort_order<class_OpenXRCompositionLayer_property_sort_order>` 设置为负值），同时在 Godot 渲染的所有内容上“打一个洞”，以便该层仍然可见。

这可用于创建合成层与 Godot 渲染的所有内容存在于同一 3D 空间中的幻觉，使对象看起来既从合成层的后面又从合成层的前面经过。

.. rst-class:: classref-item-separator

----

.. _class_OpenXRCompositionLayer_property_layer_viewport:

.. rst-class:: classref-property

:ref:`SubViewport<class_SubViewport>` **layer_viewport** :ref:`🔗<class_OpenXRCompositionLayer_property_layer_viewport>`

.. rst-class:: classref-property-setget

- |void| **set_layer_viewport**\ (\ value\: :ref:`SubViewport<class_SubViewport>`\ )
- :ref:`SubViewport<class_SubViewport>` **get_layer_viewport**\ (\ )

合成层上渲染的 :ref:`SubViewport<class_SubViewport>`\ 。

.. rst-class:: classref-item-separator

----

.. _class_OpenXRCompositionLayer_property_sort_order:

.. rst-class:: classref-property

:ref:`int<class_int>` **sort_order** = ``1`` :ref:`🔗<class_OpenXRCompositionLayer_property_sort_order>`

.. rst-class:: classref-property-setget

- |void| **set_sort_order**\ (\ value\: :ref:`int<class_int>`\ )
- :ref:`int<class_int>` **get_sort_order**\ (\ )

合成层的排序顺序。数字较大的层显示在数字较小的层之前。

\ **注意：**\ 使用回退网格时无效。

.. rst-class:: classref-section-separator

----

.. rst-class:: classref-descriptions-group

方法说明
--------

.. _class_OpenXRCompositionLayer_method_intersects_ray:

.. rst-class:: classref-method

:ref:`Vector2<class_Vector2>` **intersects_ray**\ (\ origin\: :ref:`Vector3<class_Vector3>`, direction\: :ref:`Vector3<class_Vector3>`\ ) |const| :ref:`🔗<class_OpenXRCompositionLayer_method_intersects_ray>`

返回给定射线与合成层相交的 UV 坐标。\ ``origin`` 和 ``direction`` 必须位于全局空间中。

如果射线不相交，则返回 ``Vector2(-1.0, -1.0)``\ 。

.. rst-class:: classref-item-separator

----

.. _class_OpenXRCompositionLayer_method_is_natively_supported:

.. rst-class:: classref-method

:ref:`bool<class_bool>` **is_natively_supported**\ (\ ) |const| :ref:`🔗<class_OpenXRCompositionLayer_method_is_natively_supported>`

如果 OpenXR 运行时本身支持该合成层类型，则返回 true。

\ **注意：**\ 仅在 OpenXR 会话启动后才会返回准确结果。

.. |virtual| replace:: :abbr:`virtual (本方法通常需要用户覆盖才能生效。)`
.. |const| replace:: :abbr:`const (本方法无副作用，不会修改该实例的任何成员变量。)`
.. |vararg| replace:: :abbr:`vararg (本方法除了能接受在此处描述的参数外，还能够继续接受任意数量的参数。)`
.. |constructor| replace:: :abbr:`constructor (本方法用于构造某个类型。)`
.. |static| replace:: :abbr:`static (调用本方法无需实例，可直接使用类名进行调用。)`
.. |operator| replace:: :abbr:`operator (本方法描述的是使用本类型作为左操作数的有效运算符。)`
.. |bitfield| replace:: :abbr:`BitField (这个值是由下列位标志构成位掩码的整数。)`
.. |void| replace:: :abbr:`void (无返回值。)`
