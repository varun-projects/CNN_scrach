cd /usr/local/hadoop/etc/hadoop  

cat > core-site.xml << EOL  
<configuration>  
<property>  
<name>fs.default.name</name>  
<value>hdfs://localhost:9000</value>  
</property>  
</configuration>  
EOL  

cp mapred-site.xml.template mapred-site.xml  
cat > mapred-site.xml << EOL  
<configuration>  
<property>  
<name>mapreduce.framework.name</name>  
<value>yarn</value>  
</property>  
</configuration>  
EOL  

cat > yarn-site.xml << EOL  
<configuration>  
<property>  
<name>yarn.nodemanager.aux-services</name>  
<value>mapreduce_shuffle</value>  
</property>  
</configuration>  
EOL  

cat > hdfs-site.xml << EOL  
<configuration>  
<property>  
<name>dfs.replication</name>  
<value>1</value>  
</property>  
<property>  
<name>dfs.name.dir</name>  
<value>file:///home/hadoop/hadoopinfra/hdfs/namenode </value>  
</property>  
<property>  
<name>dfs.data.dir</name>  
<value>file:///home/hadoop/hadoopinfra/hdfs/datanode </value >  
</property>  
</configuration>  
EOL  
