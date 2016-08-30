# jboss-deploy Cookbook

This cookbook deploys war files in jboss-eap server for both `standalone` and `domain` modes. 

## Requirements

### Platforms

- RHEL/CentOS
- jboss-eap 6.4

### Chef

- Chef 12.0 or later


## Attributes


### jboss-deploy::default

## Custom Resources

### deployer

The full syntax for all the properties that are available to the `deployer` resource is:

```

deployer 'name' do
    
      file_loc		String, default: '/tmp'
      owner 		String, default: 'root'
      group 		String, default: 'root'
      mode 		String, default: '644'
      package_url 	String
      checksum 		String
      module_name 	String
      host 		String, default: '127.0.0.1'
      offset 		Integer, default: 0
      jboss_mode 	String, default: 'standalone'
      jboss_home 	String, default: '/opt/jboss/'
      mgmtport 		Integer, default: 9999
      action        Symbol, default: deploy
      
end

```
where

* `file_loc` - determines the package download location. (temporary)
* `owner` - the OS user.
* `group` - the OS user group.
* `mode` - defines the permissions.
* `package_url` - the package URL.
* `checksum` - the checksum of the package. (sha256)
* `module_name` - defines the name of the module.
* `host` - the host name for `cli` access.
* `offset` - specifies the offset of the jboss instances.
* `jboss_mode` -  defines the jboss mode, default `standalone`.
* `jboss_home` - Jboss home directory.
* `mgmtport` - Jboss management port.
* `action` must be set as `deploy` or `undeploy`.

### jmodule

The full syntax for all the properties that are available to the `jmodule` resource is:

```

jmodule 'name' do
    
<<<<<<< HEAD
      owner 		String, default: 'root'
      module_name 	String
      host 		String, default: '127.0.0.1'
      offset 		Integer, default: 0
      jboss_home 	String, default: '/opt/jboss/'
      mgmtport 		Integer, default: 9999
      jdbc_loc		String
      dep_list		String
      jdbc_driver_name	String
      class_name	String
      action        	Symbol, default: create
=======
      _owner 		    String, default: 'root'
      _module_name 	    String
      _host 		    String, default: '127.0.0.1'
      _offset 		    Integer, default: 0
      _jboss_mode 	    String, default: 'standalone'
      _jboss_home 	    String, default: '/opt/jboss/'
      mgmtport 		    Integer, default: 9999
      _jdbc_loc		    String
      _dep_list		    String
      _jdbc_driver_name	String
      _class_name	    String
      action            Symbol, default: deploy
>>>>>>> 9bd47123648ec0974a76a67260156a037f177bdd
      
end


```
where

* `owner` - the OS user.
* `module_name` - defines the name of the module
* `host` - the host name for `cli` access.
* `offset` - specifies the offset of the jboss instances.
* `jboss_home` - Jboss home directory.
* `mgmtport` - Jboss management port.
* `jdbc_loc` - `jdbc` driver location.
* `dep_list` - specifies the list of dependencies.
* `jdbc_driver_name` - defines the driver name.
* `class_name` - defines the fully qualified class.
* `action` must be set as `create`.

### jmodule

The full syntax for all the properties that are available to the `jmodule` resource is:

```

datasource 'name' do

      owner 		String, default: 'root'
      host 		String, default: '127.0.0.1'
      offset 		Integer, default: 0
      jboss_home 	String, default: '/opt/jboss/'
      mgmtport 		Integer, default: 9999
      jdbc_loc		String
      dep_list		String
      jdbc_driver_name	String
      class_name	String
      user		String
      password		String
      action        	Symbol, default: create
      
end


* `owner` - the OS user.
* `module_name` - defines the name of the module
* `host` - the host name for `cli` access.
* `offset` - specifies the offset of the jboss instances.
* `jboss_home` - Jboss home directory.
* `mgmtport` - Jboss management port.
* `jdbc_loc` - `jdbc` driver location.
* `dep_list` - specifies the list of dependencies.
* `jdbc_driver_name` - defines the driver name.
* `class_name` - defines the fully qualified class.
* `action` must be set as `create`.


## Usage

### jboss-deploy::default

Just include `jboss-deploy` in your node's `run_list`:

```json
{
  "name":"my_node",
  "run_list": [
    "recipe[jboss-deploy]"
  ]
}
```

## Clone

git clone https://github.com/jantwisted/chef-jboss-deploy.git

## Contributing

1. Fork the repository on Github
2. Create a named feature branch (like `add_component_x`)
3. Write your change
4. Write tests for your change (if applicable)
5. Run the tests, ensuring they all pass
6. Submit a Pull Request using Github

## License and Authors

Authors: Janith (janith@member.fsf.org)

