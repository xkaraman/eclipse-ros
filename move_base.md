
<node pkg="move_base" type="move_base" respawn="false" name="move_base" output="screen">
    
    <!--Namespace to prepend to parameters inside yaml files -->
    <rosparam file="$(find husky_navigation)/config/costmap_common.yaml" command="load" ns="global_costmap" />
    <rosparam file="$(find husky_navigation)/config/costmap_common.yaml" command="load" ns="local_costmap" />

    <!-- 
	In order to load more paramaters there are two ways:
	1) Load yaml file with rosparam <rosparam file="$(find package)/config/costmap_local.yaml" command="load" ns="local_costmap" /> including the namespace and yaml file with no dictionary for local_costmap.
        Ex Yaml file.
	param: value
	param1: value

	2) Load yaml file rosparam <rosparam file="$(find package)/config/costmap_local.yaml" command="load" /> with no namespace. Yaml file must specify the namespace as a dictionary at start of file same as namespace you need to modify. Check common_costmap namespace `ns=value`.
	Ex YAML file.
	local_costmap:
	param:	value
	param2:	value
    -->

    <rosparam file="$(find husky_navigation)/config/costmap_local.yaml" command="load" ns="local_costmap" />
</node>
