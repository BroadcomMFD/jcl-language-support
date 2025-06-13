<div id="header" align="center">

[![GitHub issues](https://img.shields.io/github/issues-raw/BroadcomMFD/jcl-language-support?style=flat-square)](https://github.com/BroadcomMFD/jcl-language-support/issues)
[![slack](https://img.shields.io/badge/chat-on%20Slack-blue?style=flat-square)](https://join.slack.com/t/che4z/shared_invite/zt-22b0064vn-nBh~Fs9Fl47Prp5ItWOLWw
)
</div>

# JCL Language Support

JCL Language Support enhances the JCL programming experience of your IDE. The extension leverages the language server protocol to provide snippets, syntax highlighting and coloring. JCL Language Support is available as a VS Code extension.

Any file that contains a jobcard or that uses the extension `.jcl` or `.cntl` is recognized as a JCL file.

## Prerequisites

There are no client or server-side prerequisites for JCL Language Support.

## Integrate with Zowe Explorer and JCL Check

Integrate this extension with [Zowe Explorer](https://marketplace.visualstudio.com/items?itemName=Zowe.vscode-extension-for-zowe) and set up a Zowe profile to enable hyperlinks to PDS members and USS files in your JCL code. You can also use Zowe Explorer to submit jobs, and to access your mainframe data sets containing JCL directly from VS Code.

If you use [JCLCheck™ Workload Automation](https://techdocs.broadcom.com/jclcheck), we also recommend that you install the JCL Check extension for VS Code. The JCL Check extension enables you to generate reports in VS Code through the JCLCheck REST API.

<a href="https://www.openmainframeproject.org/all-projects/zowe/conformance"><img alt="This extension is Zowe v3 conformant" src="https://artwork.openmainframeproject.org/other/zowe-conformant/zowev3/explorer-vs-code/color/zowe-conformant-zowev3-explorer-vs-code-color.png" width=260 height=195 /></a>

## Features

JCL Language Support provides the following JCL syntax awareness features:

### Syntax Highlighting

The extension enables syntax highlighting for JCL code.

### Syntax Coloring

Contrasting colors are used in displayed code for ease of identifying and distinguishing keywords, variables and comments.

### Hyperlinks

If you use the Zowe Explorer extension and have a Zowe profile configured, PDS members and USS paths display as hyperlinks. This feature is enabled for PDS members specified in the format DSN(MEMBER) in `DSN=` parameters, and USS paths that are specified in `PATH=` parameters. <kbd>CTRL</kbd>+click the hyperlink to open the PDS member or USS folder in Zowe Explorer.

Only full paths which contain no wildcards display as hyperlinks.

### Code Snippets

Before you write your JCL code from scratch, search the snippet library for useful templates.

1. Press <kbd>F1</kbd> to open the command palette and run the command **Snippets: Insert Snippet**.
2. Choose the type of snippet you want to insert.
3. Fill in the templated values to complete the JCL statement.

You can also type the name of a snippet in the editor and use the VS Code autocomplete feature to add the snippet.
