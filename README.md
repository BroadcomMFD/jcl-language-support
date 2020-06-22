<!-- omit in toc -->
# JCL Language Support

[![license](https://img.shields.io/badge/license-Broadcom-green)](/LICENSE)
[![downloads](https://img.shields.io/visual-studio-marketplace/d/broadcomMFD.jcl-language-support)](https://marketplace.visualstudio.com/items?itemName=broadcomMFD.jcl-language-support)
[![issues](https://img.shields.io/github/issues-raw/BroadcomMFD/jcl-language-support)](https://github.com/BroadcomMFD/jcl-language-support/issues)

The JCL Language Support extension provides an interface in VS Code for developers and system administrators to interact with Job Control Language (JCL) on IBM z/OS mainframes. Edit JCL in a local environment complete with syntax highlighting, linting, and access to a library of sample job snippets. Integrate this extension with CA JCLCheck Workload Automation™ to ensure quality before submitting jobs. The extension provides the following benefits:

- Edit JCL in VS Code to enhance developer productivity.
- Use the syntax highlighting, linting, and auto-complete features to write JCL efficiently.
- Ensure that JCL is valid prior to job submission by integrating with CA JCLCheck on the mainframe.
- Produce CA JCLCheck reports in markdown format to share with your team.
- Access a library of useful JCL snippets.

**Tips:**

- Use this extension in conjunction with [Zowe Explorer](https://marketplace.visualstudio.com/items?itemName=Zowe.vscode-extension-for-zowe) to enable a suite of mainframe functionality in VS Code.
- The syntax highlighting capability is based on the [ibm-jcl extension](https://github.com/dkelosky/vscode-ibm-jcl).

<!-- omit in toc -->
## Contents

- [Software Requirements](#software-requirements)
- [Configuring](#configuring)
- [Using](#using)

## Software Requirements

You can use the JCL syntax highlighting and linting features features *without* installing any prerequisite software.

If you want to use CA JCLCheck reporting features, meet the following requirements:

- An instance of CA JCLCheck Workload Automation v12.0 is installed and configured on a mainframe system with latest maintenance applied.
- [Zowe CLI](https://docs.zowe.org/stable/user-guide/cli-installcli.html) is installed on your PC.
- The [CA JCLCheck Plug-in for Zowe CLI](https://techdocs.broadcom.com/content/broadcom/techdocs/us/en/ca-mainframe-software/devops/ca-brightside/3-0/ca-brightside-command-line-interface-cli/available-cli-plug-ins/ca-jclcheck-workload-automation-plug-in-for-zowe-cli.html) is installed to Zowe CLI.

## Configuring

To connect with a JCLCheck instance on the mainframe, create a `jclcheck` service profile on your computer using the CA JCLCheck Plug-in for Zowe CLI. For information, see the "Create a User Profile" section in the [plug-in documentation](https://techdocs.broadcom.com/content/broadcom/techdocs/us/en/ca-mainframe-software/devops/ca-brightside/3-0/ca-brightside-command-line-interface-cli/available-cli-plug-ins/ca-jclcheck-workload-automation-plug-in-for-zowe-cli.html) on Broadcom TechDocs.

After you create the profile in the CLI, it becomes available for use in VS Code. You can now perform actions in the extension against your default profile.

You can use Zowe CLI to set which profile is your default. Issue the following command:

```sh
zowe profiles set-default jclcheck <profileName>
```

**Note:** Future enhancements will provide the ability to create profiles directly in the VS Code interface.

### Advanced configuration

To access extension settings, navigate to **File > Settings**, then select **Extensions > JCL configuration**.

You can configure the following options:

- **JCLCheck features -** Enable the linting and reporting features provided by the CA JCLCheck REST API. Ensure that you meet the software requirements before you use these features. (Default: Off)
- **Automatic linting on save -** Choose to perform linting manually, or automatically lint for each local save. You must enable the JCLCheck features option to use linting. (Default: On)
- **Reports location -** Specify the local folder where JCLCheck reports are saved. If you leave the setting blank, the extension prompts you for a location when you generate a report.
- **Server tracing -** Traces communication between VS Code and the language server. Specify Off, Messages, or Verbose. (Default: Off)
- **Syntax highlighting rules -** Configure syntax highlighting settings. For example, highlight the continuation column:

    ```json
    "[jcl]" : { "editor.rulers" : [71, 72, 80]},
    ```

## Using

Review the following use cases to understand how to use the JCL Language Support extension:

### Accessing JCL locally

This extension *does not* provide the ability for you to download from, upload to, or submit jobs on the mainframe. To access mainframe code on your computer, use a tool such as Zowe CLI or Zowe Explorer.

### JCL syntax highlighting

For basic syntax highlighting and symbol resolution, use the shortcut `Ctrl/Cmd + Shift + O`.

![Syntax highlighting](/docs/images/jcl-hilite.png)

### JCL Linting

Perform linting to check your JCL for programmatic or stylistic errors. You can perform linting manually, or enable automatic linting on save.

**Note:** To use linting, meet the software requirements and enable the "JCLCheck features" option. Automatic linting is enabled by default. See [Configuring](#configuring) for more information.

**Follow these steps:**

1. Open the command palette with `Ctrl/Cmd + Shift + P`
2. Type "Check your JCL".
3. Click the command or press Enter to perform linting.

    JCL problems are highlighted in your code and displayed in the VS Code **Problems** view.

![JCLCheck linting](/docs/images/jck-linting.gif)

### Producing and sharing JCLCheck reports

Run CA JCLCheck against your code and produce convenient reports in markdown format.

**Note:** To use reporting, meet the software requirements and enable the "JCLCheck features" option. See [Configuring](#configuring) for more information.

**Follow these steps:**

1. Open the command palette with `Ctrl/Cmd + Shift + P`
2. Type "Generate JCL report".
3. Click the command or press Enter to generate a report.
4. When prompted for a filename, enter a location where the report should be saved and click **OK** to continue.

The report opens in VS Code after it is generated. Reports are created in the folder that you specified in the prompt, or that you specify in the extension settings.

![JCLCheck report generation](/docs/images/jck-report.gif)

**Tip:** If you want to convert your JCLCheck report from Markdown format into PDF, HTML, PNG, or JPEG, we recommend using the extension [Markdown PDF by yzane](https://marketplace.visualstudio.com/items?itemName=yzane.markdown-pdf).

### Using JCL snippets

Before you write JCL from scratch, check the snippet library for useful job templates.

**Follow these steps:**

1. Open the command palette with `Ctrl/Cmd + Shift + P`
2. Type "Insert Snippet".
3. Click the command or press Enter.
4. Choose the type of snippet you want to insert.
5. Fill in the templated values to complete the JCL statement.

For a quicker way to access the snippets:

1. Begin typing the name of a snippet (e.g. IEFBR14) in the editor.
2. VS Code autocomplete should suggest the snippet.
3. Select the suggested snippet and press Enter.

![Snippets](/docs/images/jcl-snippets.gif)

### Creating JCL snippets

You can add your own JCL templates to the snippet library.

Navigate to **File > Preferences > User Snippets** and select the JCL language.

Refer to [Create your own snippets](https://code.visualstudio.com/docs/editor/userdefinedsnippets#_create-your-own-snippets) in the VS Code documentation for detailed information about creating the snippet.

For more information about this extension, please visit the [documentation on Broadcom TechDocs](https://techdocs.broadcom.com/content/broadcom/techdocs/us/en/ca-mainframe-software/automation/ca-jclcheck-workload-automation/12-0/building/interfaces-with-other-products/jcl-language-support-extension-for-vs-code.html).

---------------------------------------------------------------
<!-- omit in toc -->
## **Technical Assistance and Support for JCL Language Support extension**

The JCL Language Support extension is made available to customers on Visual Studio Code Marketplace in accordance with the terms and conditions contained in the provided End-User License Agreement (EULA).

If you are on active support for CA JCLCheck Workload Automation or CA Brightside, technical assistance and support is provided to Broadcom customers in accordance with the terms, guidelines, details and parameters located within Broadcom’s “Working with Support” guide located at:

https://techdocs.broadcom.com/us/product-content/admin-content/ca-support-policies.html?intcmp=footernav

This support generally includes:

- Telephone and online access to technical support
- Ability to submit new incidents 24x7x365
- 24x7x365 continuous support for Severity 1 incidents
- 24x7x365 access to CA Support Online
- Interactive remote diagnostic support

Technical support cases must be submitted to Broadcom in accordance with guidance provided in “Working with Support”.

Note: To receive technical assistance and support, you must remain compliant with “Working with Support”, be current on all applicable licensing and maintenance requirements, and maintain an environment in which all computer hardware, operating systems, and third party software associated with the affected Broadcom CA software are on the releases and version levels from the manufacturer that Broadcom designates as compatible with the software.  Changes you elect to make to your operating environment could detrimentally affect the performance of Broadcom CA software and Broadcom shall not be responsible for these effects or any resulting degradation in performance of the Broadcom CA software.  Severity 1 cases must be opened via telephone and elevations of lower severity incidents to Severity 1 status must be requested via telephone.

------------------------------------------------------------------------------------------------
Copyright © 2020 Broadcom. The term "Broadcom" refers to Broadcom Inc. and/or its subsidiaries.
