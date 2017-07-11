# docker 发布接入

## 一、约定

原部署目录：

\${user.home}/tqdeploy/\${projectName}/\${projectName}/\${projectName}_\${number}

原日志目录： 

\${user.home}tqdeploy/\${projectName}/\${projectName}/\${projectName}_\${number}/log

## 二、接口定义

批量功能由JAVA 程序多次调用

1、启动容器(如果已经启动，先停止，再启动)  

| 参数          | 值    | 说明   |
| :---------- | ---- | ---- |
| projectName | 应用名称 |      |
| ip          |      |      |
| number      |      |      |
| type        | war  |      |
| jobName     |      |      |
| 附件：ROOT.war |      |      |

响应：流的形式返回：启动日志。



2、重启

| 参数          | 值    | 说明   |
| :---------- | ---- | ---- |
| projectName |      |      |
| ip          |      |      |
| number      |      |      |
| type        | war  |      |
|             |      |      |

响应： 流的形式返回：启动日志。

3、停止

| 参数          | 值    | 说明   |
| :---------- | ---- | ---- |
| projectName |      |      |
| ip          |      |      |
| number      |      |      |
| type        | war  |      |
|             |      |      |

响应： 流的形式返回：停止日志。

4、回滚

| 参数          | 值    | 说明   |
| :---------- | ---- | ---- |
| projectName |      |      |
| ip          |      |      |
| number      |      |      |
| type        | war  |      |
| jobName     |      |      |
| 附件：ROOT.war |      |      |



5、健康检查

| 参数          | 值    | 说明   |
| :---------- | ---- | ---- |
| projectName |      |      |
| ip          |      |      |
| number      |      |      |
| type        | war  |      |

返回： http response  