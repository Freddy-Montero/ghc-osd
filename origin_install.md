# Installing the OpenShift CLI
### Command Line Interface

OpenShift ships with a feature rich web console as well as command line tools to provide users with a nice interface to work with applications deployed to the platform. The OpenShift tools are a single executable written in the Go programming language and is available for the following operating systems:

* Microsoft Windows
* Apple OS X
* Linux

You might already have the OpenShift CLI available on your environment. You can verify it by running an oc command:

```
$ oc version
```

You should see the following (or something similar):

```
oc v3.10.0+dd10d1
kubernetes v1.10.0+b81c8f8
```

If the oc doesn’t exist or you have an older version of the OpenShift CLI, follow the next sections to install or update the OpenShift CLI.

### Download and Install OpenShift CLI on Windows

Download the the OpenShift CLI tool for [Microsoft Windows](https://github.com/openshift/origin/releases/download/v3.10.0/openshift-origin-client-tools-v3.10.0-dd10d17-windows.zip)

Once the file has been downloaded, you will need to extract the contents as it is a compressed archive. I would suggest saving this file to the following directories:

```
C:\OpenShift
```

In order to extract a zip archive on windows, you will need a zip utility installed on your system. With newer versions of windows (greater than XP), this is provided by the operating system. Just right click on the downloaded file using file explorer and select to extract the contents.

Now you can add the OpenShift CLI tools to your PATH. Because changing your PATH on windows varies by version of the operating system, we will not list each operating system here. However, the general workflow is right click on your computer name inside of the file explorer. Select Advanced system settings. I guess changing your PATH is considered an advanced task? :) Click on the advanced tab, and then finally click on Environment variables. Once the new dialog opens, select the Path variable and add ;C:\OpenShift at the end. For an easy way out, you could always just copy it to C:\Windows or a directory you know is already on your path. For more detailed instructions:

* [Windows XP](https://support.microsoft.com/en-us/kb/310519)
* [Windows Vista](http://banagale.com/changing-your-system-path-in-windows-vista.htm)
* [Windows 7 - Windows 10](http://geekswithblogs.net/renso/archive/2009/10/21/how-to-set-the-windows-path-in-windows-7.aspx)

At this point, we should have the oc tool available for use. Let’s test this out by printing the version of the oc command:

```
> oc version
```

You should see the following (or something similar):

```
oc v3.10.0+dd10d1
kubernetes v1.10.0+b81c8f8
```

If you get an error message, you have not updated your path correctly. If you need help, raise your hand and the instructor will assist.

### Download and Install OpenShift CLI on Linux

Download the the OpenShift CLI tool for [Linux 64](https://github.com/openshift/origin/releases/download/v3.10.0/openshift-origin-client-tools-v3.10.0-dd10d17-linux-64bit.tar.gz)

Once the file has been downloaded, you will need to extract the contents as it is a compressed archive. I would suggest saving this file to the following directories:

```
~/openShift
```

Open up a terminal window and change to the directory where you downloaded the file. Once you are in the directory, enter in the following command:
	The name of the oc packaged archive may vary. Adjust accordingly.

```
$ tar zxvf oc-linux.tar.gz
```

The tar.gz file name needs to be replaced by the entire name that was downloaded in the previous step.

Now you can add the OpenShift CLI tools to your PATH.

```
$ export PATH=$PATH:~/openShift
```

At this point, we should have the oc tool available for use. Let’s test this out by printing the version of the oc command:

```
$ oc version
```

You should see the following (or something similar):

```
oc v3.10.0+dd10d1
kubernetes v1.10.0+b81c8f8
```

If you get an error message, you have not updated your path correctly. If you need help, raise your hand and the instructor will assist.

### Download and Install OpenShift CLI on Mac

Download the the OpenShift CLI tool for [Mac](https://github.com/openshift/origin/releases/download/v3.10.0/openshift-origin-client-tools-v3.10.0-dd10d17-mac.zip)

Once the file has been downloaded, you will need to extract the contents as it is a compressed archive. I would suggest saving this file to the following directories:

```
~/openShift
```

Open up a terminal window and change to the directory where you downloaded the file. Once you are in the directory, enter in the following command:
	The name of the oc packaged archive may vary. Adjust accordingly.

```
$ tar zxvf oc-macosx.tar.gz
```

The tar.gz file name needs to be replaced by the entire name that was downloaded in the previous step.

Now you can add the OpenShift CLI tools to your PATH.

```
$ export PATH=$PATH:~/openShift
```

At this point, we should have the oc tool available for use. Let’s test this out by printing the version of the oc command:

```
$ oc version
```

You should see the following (or something similar):

```
oc v3.10.0+dd10d1
kubernetes v1.10.0+b81c8f8
```

If you get an error message, you have not updated your path correctly. If you need help, raise your hand and the instructor will assist.

### Tab Completion

The OpenShift command line tool supports the ability to use tab completion for the popular zsh and bash shells. This suits the needs of users using either Linux or OS X. If you are using Microsoft Windows, never fear, we will discuss some ways to get tab completion working on that operating system as well.
Tab completion on Mac and Linux

If you are on the Mac operating system, you will need to ensure that you have the bash-completion project installed. This can be accomplished using the popular brew system:

```
$ brew install bash-completion
```

If you’re on Linux, ensure you have bash-completion installed using your package manager (dnf, yum apt-get,…​)

Once bash-completion package is available in your machine, to enable tab completion in your shell, you can simply enter in the following command from your terminal

```
$ oc completion bash >> oc_completion.sh
$ source oc_completion.sh
```

Alternatively, you can add this to your .bashrc file.

If you are using zsh, you can run the following command:

```
$ source <(oc completion zsh)
```

Alternatively, you can add this to your .zshrc file.

### Tab completion on Windows

For Windows users, things become a bit more tricky. You could of course use the Linux Subsystem for Windows but you may want to consider using a combination of babun and cmder. For a full list of instructions, you can check out the following blog post:

    https://blog.openshift.com/openshift-3-tab-completion-for-windows/
