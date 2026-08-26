<div id="header" align="center">

[![GitHub issues](https://img.shields.io/github/issues-raw/BroadcomMFD/jcl-language-support?style=flat-square)](https://github.com/BroadcomMFD/jcl-language-support/issues)
[![slack](https://img.shields.io/badge/chat-on%20Slack-blue)](https://join.slack.com/t/che4z/shared_invite/zt-37ewynplx-wCoabaIDxN6Ofm4_XBinZA)
[![Code4z](https://img.shields.io/badge/Code4z-marketplace-cc092f)](https://marketplace.visualstudio.com/search?term=code4z&target=VSCode)

</div>

# JCL Language Support

JCL Language Support enhances the JCL programming experience of your IDE. The extension leverages the language server protocol to provide snippets, syntax highlighting and coloring. JCL Language Support is available as a VS Code extension.

Any file that contains a jobcard or that uses the extension `.jcl` or `.cntl` is recognized as a JCL file.

<img align="left" alt="This extension is part of the Code4z experience" width="80" height="82" src="https://raw.githubusercontent.com/BroadcomMFD/code4z/refs/heads/main/icon5.png" />

JCL Language Support is part of the [Code4z](https://techdocs.broadcom.com/code4z) experience from Broadcom, which offers a modern experience for mainframe application developers. To get started with Code4z, check out our foundational [extension pack](https://marketplace.visualstudio.com/items?itemName=broadcomMFD.code4z-extension-pack).

<br />

## Address Software Requirements

There are no client or server-side software requirements for JCL Language Support.

## Integrate with Zowe Explorer and JCL Check

Integrate this extension with [Zowe Explorer](https://marketplace.visualstudio.com/items?itemName=Zowe.vscode-extension-for-zowe) and set up a default `zosmf` profile to enable hyperlinks to data sets and USS files in your JCL code. You can also use Zowe Explorer to submit jobs, and to access your mainframe data sets that contain JCL directly from VS Code.

If you use [JCLCheck™ Workload Automation](https://techdocs.broadcom.com/jclcheck), we also recommend that you install the [JCL Check extension for VS Code](https://marketplace.visualstudio.com/items?itemName=broadcomMFD.jcl-check-support). The JCL Check extension enables you to generate reports in VS Code through the JCLCheck REST API.

<div align="center">
<a href="https://www.openmainframeproject.org/all-projects/zowe/conformance"><img alt="This extension is Zowe v3 conformant" src="https://artwork.openmainframeproject.org/other/zowe-conformant/zowev3/explorer-vs-code/color/zowe-conformant-zowev3-explorer-vs-code-color.png" width=208 height=156 /></a>
</div>

## Features

JCL Language Support provides the following JCL syntax awareness features:

### Syntax Highlighting and Coloring

The extension enables syntax highlighting for JCL code. Contrasting colors are used in displayed code for ease of identifying and distinguishing name fields, statements, parameters, commands, variables, and comments.

Statements that are ignored because they follow a null statement are colored in a darker tone.

### Syntax Check

JCL Language Support checks for errors in names of statements, and enforces column limits and some other rudimentary syntactic rules.

For comprehensive syntactic and semantic linting, we recommend the use of [JCLCheck™ Workload Automation](https://techdocs.broadcom.com/jclcheck) and the [JCL Check extension for VS Code](https://marketplace.visualstudio.com/items?itemName=broadcomMFD.jcl-check-support).

### Outline View and Breadcrumbs

The extension enables outline view and the breadcrumbs navigation bar at the top of the edit window, which show the structure of elements within the program and allow easy navigation between them.

### Hyperlinks

If you use the Zowe Explorer extension and have a default `zosmf` profile in your team configuration file, data set names and USS paths in the code display as hyperlinks. This feature is enabled for data sets in `DSN=` parameters, and USS paths that are specified in `PATH=` parameters. <kbd>CTRL</kbd>+click the hyperlink to open the data set or USS file in Zowe Explorer.

The hyperlink feature only works on PDS members and sequential files. Other types of data set are still linked but cannot be opened. The hyperlink feature also does not work on wildcarded values.

If a data set name or USS path contains a variable that is defined in the code, the data set or USS file can still be opened with a hyperlink.

### Code Snippets

Before you write your JCL code from scratch, search the snippet library for useful templates.

1. Press <kbd>F1</kbd> to open the command palette and run the command **Snippets: Insert Snippet**.
2. Choose the type of snippet you want to insert.
3. Fill in the templated values to complete the JCL statement.

You can also type the name of a snippet in the editor and use the VS Code autocomplete feature to add the snippet.
