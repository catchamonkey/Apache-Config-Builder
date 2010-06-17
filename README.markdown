#Apache Config Builder

Define a VirtualHost template, run build_config with a few optional --flags

build_config will create your VirtualHost declaration in the file you specify, 
other tasks will be performed depending on --flags used

Your template should look like this

    <VirtualHost [IP]:[PORT]>
      DocumentRoot [DOCUMENT_ROOT]
      DirectoryIndex [DIRECTORY_INDEX]
      ServerName [HOSTNAME]:[PORT]
      <Directory [DOCUMENT_ROOT]>
        AllowOverride All
        Allow from All
      </Directory>
    </VirtualHost>
    
Each of the [] blocks defines a tag that can be modified by the script.
You can optionally define default for some flags that will be used unless overridden.
To define a default simply put the default value after the NAME, seperated by a colon:
e.g. [PORT:80] or [IP:*]