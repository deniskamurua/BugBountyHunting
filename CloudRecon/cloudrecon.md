[Getting Apex Domains from cloud Data ] RUN THE COMMAND FROM [~/Documents/ToolBox/CloudRecon]
# cat *.txt | grep -F ".dell.com" | awk -F'-- ' '{print $2}'| tr ' ' '\n' | tr '[' ' ‘| sed 's/ //’| sed 's/\]//’| grep -F ".dell.com“ | sort -u
