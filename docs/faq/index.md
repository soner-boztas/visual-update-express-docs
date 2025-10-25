---
hide:
  - navigation
  - toc
---

# Frequently Asked Questions

??? question "Are there any costs associated with using Visual Update?"

    For non-commercial use, Visual Update is completely free of charge (Visual Update Community Edition).
    However, if you intend to use Visual Update for commercial purposes, you must acquire a valid Visual Update Pro
    Edition license. You can find more information about the different license types in the
    [License](../license/index.md) section.

??? question "Is there any functional difference between Visual Update Community Edition and the commercial editions?"

    No, there are no functional differences. All editions provide the same functionality for creating and deploying
    DUP's. The only difference is that the commercial editions allow commercial usage, do not contain a brand banner and
    come with priority technical support.

??? question "Do DUP's created with Visual Update depend on any runtime environment (such as .NET)?"

    No, not at all! DUP's created with Visual Update have only minimal dependencies on the Win 32 API and are 
    compatible even with older Windows versions.

??? question "Are DUP's compiled native machine code?"

    Yes! The program code of the Visual Update DUP stub is pure C code compiled with
    [gcc](https://gcc.gnu.org/).

??? question "Can I deploy DUP's together with any application, regardless of the technology used?"

    Yes, indeed. You can deploy DUP's together any application, regardless of the programming language and technology
    used for its development.

??? question "What is the preferred support channel for Visual Update?"

    If you own a commercial license, you can contact our support team directly via email at
    support@visualupdate.net.
    If you do not own a commercial license, i.e. you are using Visual Update Community Edition, refer to our
    [online forums](https://installforge.net/forums/). There are other Visual Update users around who will be happy to
    help you with your questions and problems.

??? question "DUP's I have created always request for admin (elevated) rights. Can I change this behavior?"

    No, this behavior is implemented by design.

??? question "Can I use my own translation for the [DUP Wizard]?"

    No, Visual Update does not provide any functionality for using custom translations. If you own a Pro license, you
    can request additional languages to be supported in future releases by contacting our support team:
    support@visualupdate.net

??? question "Do I need to have PHP or any other back-end technology available on the [server environment]?"

    No, all you need is at least a minimal HTTP/web server.

??? question "How can I integrate the Visual Update build system into a CD-pipeline?"

    Yes, this is supported through the InstallForge CLI builder (available with InstallForge version 1.5.0+).
    You can find more information about this in the [InstallForge documentation](https://docs.installforge.net/).
