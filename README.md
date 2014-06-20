osgi-4-qt
=========

A Qt5 based client (GUI and Non-GUI) framework loosely based on OSGi

The framework uses Qt5 and is based loosely on the OSGi specification. The purpose of this framework is
to achieve the following goals:

1. Achieve binary level integration and reuse. Using OO designs, we reuse classes via inheritance and encapsulation,
    but it still requires source code level work when it comes to software development. This framework allows
    encapsulation of UI and logic into one module which I call plugin, and provides services to other plugins, similar
    to the OSGi Bundle and Service structure. Thus, a written and tested plugin need not be inspected at the source
    code level, but only redeployed to a new product.
    
2. Achieve dynamic loading of plugins. A plugin normally consist of two parts, a plugin description file which is an xml
    file that is separate from the plugin binary, and the plugin binary itself in the form of a shared library, under Windows
    systems, in the form of a dll. It can also have an optional third part, the i18n files. By reading the description file,
    the framework can decide whether it should load a plugin or not at runtime. Thus by grouping different plugins
    together, developers automatically get a new application.
    
3. Dynamic replacement of UI. Plugins can have UI components. The framework now wraps UI components into
    form of abstract managers (menu bar manager, tool bar manager, content panel manager, side panel manager,
    and status bar manager). Plugins normally do not care about their parents' layouts or representation, thus by
    replacing the managers with a different implementation, the user gets a new look and feel.
    
4. Centralized logging and security check.

5. Automatic application upgrade.
