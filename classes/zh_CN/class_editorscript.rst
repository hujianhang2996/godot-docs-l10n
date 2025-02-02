:github_url: hide

.. DO NOT EDIT THIS FILE!!!
.. Generated automatically from Godot engine sources.
.. Generator: https://github.com/godotengine/godot/tree/master/doc/tools/make_rst.py.
.. XML source: https://github.com/godotengine/godot/tree/master/doc/classes/EditorScript.xml.

.. _class_EditorScript:

EditorScript
============

**继承：** :ref:`RefCounted<class_RefCounted>` **<** :ref:`Object<class_Object>`

可用于为编辑器添加扩展功能的基础脚本。

.. rst-class:: classref-introduction-group

描述
----

扩展该类并实现其 :ref:`_run<class_EditorScript_private_method__run>` 方法的脚本可以在编辑器运行时通过脚本编辑器的\ **文件 > 运行**\ 菜单选项（或按 :kbd:`Ctrl + Shift + X`\ ）执行。这对于向 Godot 添加自定义的编辑内功能很有用。对于更复杂的添加，请考虑改用 :ref:`EditorPlugin<class_EditorPlugin>`\ 。

\ **注意：**\ 扩展脚本需要启用 ``tool`` 工具模式。

\ **示例脚本：**\ 


.. tabs::

 .. code-tab:: gdscript

    @tool
    extends EditorScript
    
    func _run():
        print("Hello from the Godot Editor!")

 .. code-tab:: csharp

    using Godot;
    
    [Tool]
    public partial class HelloEditor : EditorScript
    {
        public override void _Run()
        {
            GD.Print("Hello from the Godot Editor!");
        }
    }



\ **注意：**\ 脚本在编辑器上下文中运行，这意味着输出在使用编辑器（stdout）启动的控制台窗口中可见，而不是通常的 Godot **输出**\ 停靠面板。

\ **注意：**\ EditorScript 是 :ref:`RefCounted<class_RefCounted>`\ ，这意味着它不再被引用时会被销毁。如果没有对脚本的引用，这可能会在异步操作期间导致错误。

.. rst-class:: classref-reftable-group

方法
----

.. table::
   :widths: auto

   +-----------------------------------------------+-----------------------------------------------------------------------------------------------------+
   | |void|                                        | :ref:`_run<class_EditorScript_private_method__run>`\ (\ ) |virtual|                                 |
   +-----------------------------------------------+-----------------------------------------------------------------------------------------------------+
   | |void|                                        | :ref:`add_root_node<class_EditorScript_method_add_root_node>`\ (\ node\: :ref:`Node<class_Node>`\ ) |
   +-----------------------------------------------+-----------------------------------------------------------------------------------------------------+
   | :ref:`EditorInterface<class_EditorInterface>` | :ref:`get_editor_interface<class_EditorScript_method_get_editor_interface>`\ (\ ) |const|           |
   +-----------------------------------------------+-----------------------------------------------------------------------------------------------------+
   | :ref:`Node<class_Node>`                       | :ref:`get_scene<class_EditorScript_method_get_scene>`\ (\ ) |const|                                 |
   +-----------------------------------------------+-----------------------------------------------------------------------------------------------------+

.. rst-class:: classref-section-separator

----

.. rst-class:: classref-descriptions-group

方法说明
--------

.. _class_EditorScript_private_method__run:

.. rst-class:: classref-method

|void| **_run**\ (\ ) |virtual| :ref:`🔗<class_EditorScript_private_method__run>`

当使用\ **文件 > 运行**\ 时，此方法由编辑器执行。

.. rst-class:: classref-item-separator

----

.. _class_EditorScript_method_add_root_node:

.. rst-class:: classref-method

|void| **add_root_node**\ (\ node\: :ref:`Node<class_Node>`\ ) :ref:`🔗<class_EditorScript_method_add_root_node>`

Makes ``node`` root of the currently opened scene. Only works if the scene is empty. If the ``node`` is a scene instance, an inheriting scene will be created.

.. rst-class:: classref-item-separator

----

.. _class_EditorScript_method_get_editor_interface:

.. rst-class:: classref-method

:ref:`EditorInterface<class_EditorInterface>` **get_editor_interface**\ (\ ) |const| :ref:`🔗<class_EditorScript_method_get_editor_interface>`

**已弃用：** :ref:`EditorInterface<class_EditorInterface>` is a global singleton and can be accessed directly by its name.

返回 :ref:`EditorInterface<class_EditorInterface>` 单例实例。

.. rst-class:: classref-item-separator

----

.. _class_EditorScript_method_get_scene:

.. rst-class:: classref-method

:ref:`Node<class_Node>` **get_scene**\ (\ ) |const| :ref:`🔗<class_EditorScript_method_get_scene>`

Returns the edited (current) scene's root :ref:`Node<class_Node>`. Equivalent of :ref:`EditorInterface.get_edited_scene_root<class_EditorInterface_method_get_edited_scene_root>`.

.. |virtual| replace:: :abbr:`virtual (本方法通常需要用户覆盖才能生效。)`
.. |const| replace:: :abbr:`const (本方法无副作用，不会修改该实例的任何成员变量。)`
.. |vararg| replace:: :abbr:`vararg (本方法除了能接受在此处描述的参数外，还能够继续接受任意数量的参数。)`
.. |constructor| replace:: :abbr:`constructor (本方法用于构造某个类型。)`
.. |static| replace:: :abbr:`static (调用本方法无需实例，可直接使用类名进行调用。)`
.. |operator| replace:: :abbr:`operator (本方法描述的是使用本类型作为左操作数的有效运算符。)`
.. |bitfield| replace:: :abbr:`BitField (这个值是由下列位标志构成位掩码的整数。)`
.. |void| replace:: :abbr:`void (无返回值。)`
