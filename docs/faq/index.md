# Frequently Asked Questions

??? question "Are there any costs associated with using Visual Update Express?"

    No! Visual Update Express is free to use.

??? question "Do DUP's created with Visual Update Express depend on any runtime environment (such as .NET)?"

    No, not at all! DUP's created with Visual Update Express have only minimal dependencies on the Win 32 API and are 
    compatible even with older Windows versions.

??? question "Are DUP's compiled native machine code?"

    Yes! The program code of Visual Update Express setup package executables is pure C code compiled with
    [gcc](https://gcc.gnu.org/).

??? question "Can I deploy DUP's together with any application, regardless of the technology used?"

    Yes, indeed. You can deploy DUP's together any application, regardless of the programming language and technology
    used for its development.

??? question "What is the preferred support channel for Visual Update Express?"

    The first place you should go is our [online forums](https://installforge.net/forums/). There are other 
    Visual Update Express users around who will be happy to help you with your questions and problems.

??? question "DUP's I have created always request for admin (elevated) rights. Can I change this behavior?"

    No, this behavior is implemented by design.

??? question "Can I use my own translation for the [DUP wizard]?"

    No, Visual Update Express does not provide any functionality for using custom translations.

??? question "Do I need to have PHP or any other back-end technology available on the [server environment]?"

    No, all you need is at least a minimal HTTP/web server.

??? question "How can I integrate the Visual Update [build system] into a CD-pipeline?"

    Unfortunately, this is not supported at the moment. You are only able to build DUP's from the InstallForge build
    system graphical user interface, making automation via scripts impossible. We understand this great need, though,
    and will come up with a convenient solution in the near future.
