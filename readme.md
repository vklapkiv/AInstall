
Installer for ABillS based on plugin system
===============================================

ver. 0.1
Feel free to make bugreports

Installing:
  * ABillS
  * MySQL
  * FreeRadius
  * Apache
  * Accel-PPPoE
  * Flow-tools
  * ...

Plugins are structured as plugins/Distributive_VersionArch

Plugin Format
-------------

<table>
  <tr>
    <td>
      <b>Section</b>
    </td>
    <td>
      <b>Example</b>
    </td>
  </tr>
  <tr>
    <td>
      #OS OS_NAME OS_VERSION
    </td>
    <td>
      #OS freebsd 10
    </td>
  </tr>
  <tr>
    <td>
      #COMMENTS comments for plugin
    </td>
    <td>
      #COMMENTS CentOS comment
    </td>
  </tr>
  <tr>
    <td>
      #M [module_name]:[module describe]:[command]
    </td>
    <td>
      #M mysql:MySQL:_install_mysql
    </td>
  </tr>

</table>

As command you can use shell command like 
  <b>pkg install www</b> 
or shell function:
  <b>shell_function</b>

Inside plugin you can use these functions to execute custom commands.
<table>
  <tr>
    <td>
      pre_install()
    </td>
    <td>
      executes before installing modules
    </td>
  </tr>
  <tr>
    <td>
      post_install()
    </td>
    <td>
       executes after full installation (before autoconf)
    </td>
  </tr>  
</table> 


Plugin execution flow
----------------
<table>
  <tr><td>
    Pre install 
  </td></tr>
  <tr><td>
    Install programs
  </td></tr>
  <tr><td>
    Post install
  </td></tr>
  <tr><td>
    Run misc/autoconf 
  </td></tr>
  <tr><td>
    Show result
  </td></tr>
</table>

Installer uses <b>autoconf</b> for module configuration and defining system startup.
