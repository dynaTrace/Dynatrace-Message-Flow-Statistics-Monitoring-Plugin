<html xmlns="http://www.w3.org/1999/xhtml">
<head>
    <title>Message Flow Statistics Monitoring Plugin</title>
    <meta http-equiv="Content-Type" content="text/html; charset=UTF-8"/>
    <meta http-equiv="X-UA-Compatible" content="IE=EmulateIE8" />
    <meta content="Scroll Wiki Publisher" name="generator"/>
    <link type="text/css" rel="stylesheet" href="css/blueprint/liquid.css" media="screen, projection"/>
    <link type="text/css" rel="stylesheet" href="css/blueprint/print.css" media="print"/>
    <link type="text/css" rel="stylesheet" href="css/content-style.css" media="screen, projection, print"/>
    <link type="text/css" rel="stylesheet" href="css/screen.css" media="screen, projection"/>
    <link type="text/css" rel="stylesheet" href="css/print.css" media="print"/>
</head>
<body>
                <h1>Message Flow Statistics Monitoring Plugin</h1>
    <div class="section-2"  id="112462676_MessageFlowStatisticsMonitoringPlugin-Overview"  >
        <h2>Overview</h2>
    <p>
            <img src="images_community/download/attachments/112462676/icon.png" alt="images_community/download/attachments/112462676/icon.png" class="confluence-embedded-image image-center" />
            </p>
    <p>
This monitor collects message flow statistics by connecting to the MQ Manager.    </p>
    </div>
    <div class="section-2"  id="112462676_MessageFlowStatisticsMonitoringPlugin-PluginDetails"  >
        <h2>Plugin Details</h2>
    <div class="tablewrap">
        <table>
<thead class=" "></thead><tfoot class=" "></tfoot><tbody class=" ">    <tr>
            <td rowspan="1" colspan="1">
        <p>
Plug-In Versions    </p>
            </td>
                <td rowspan="1" colspan="1">
        <p>
<a href="attachments_112591274_1_com.dynatrace.diagnostic.plugins.MessageFlowStatistics_2.0.0.jar">MessageFlowStatistics_2.0.0.jar</a>    </p>
            </td>
        </tr>
    <tr>
            <td rowspan="1" colspan="1">
        <p>
dynaTrace Versions    </p>
            </td>
                <td rowspan="1" colspan="1">
        <p>
4.2.0.3170+    </p>
            </td>
        </tr>
    <tr>
            <td rowspan="1" colspan="1">
        <p>
Author    </p>
            </td>
                <td rowspan="1" colspan="1">
        <p>
Asad Ali (asad.ali@compuware.com)    </p>
            </td>
        </tr>
    <tr>
            <td rowspan="1" colspan="1">
        <p>
License    </p>
            </td>
                <td rowspan="1" colspan="1">
        <p>
<a href="attachments_5275722_2_dynaTraceBSD.txt">dynaTrace BSD</a>    </p>
            </td>
        </tr>
    <tr>
            <td rowspan="1" colspan="1">
        <p>
Support    </p>
            </td>
                <td rowspan="1" colspan="1">
        <p>
<a href="https://community/display/DL/Support+Levels#SupportLevels-Community">Not Supported </a>    </p>
            </td>
        </tr>
    <tr>
            <td rowspan="1" colspan="1">
        <p>
Known Problems    </p>
            </td>
                <td rowspan="1" colspan="1">
        <p>
    </p>
            </td>
        </tr>
    <tr>
            <td rowspan="1" colspan="1">
        <p>
Release History    </p>
            </td>
                <td rowspan="1" colspan="1">
        <p>
2013-03-05 Initial Release    </p>
            </td>
        </tr>
</tbody>        </table>
            </div>
    </div>
    <div class="section-2"  id="112462676_MessageFlowStatisticsMonitoringPlugin-ProvidedMeasures"  >
        <h2>Provided Measures</h2>
    <p>
The following statistics are collected for each message flow:    </p>
<ul class=" "><li class=" ">    <p>
TOTAL_ELAPSED_TIME    </p>
</li><li class=" ">    <p>
ELAPSED_TIME_PER_MESSAGE    </p>
</li><li class=" ">    <p>
MAXIMUM_ELAPSED_TIME    </p>
</li><li class=" ">    <p>
MINIMUM_ELAPSED_TIME    </p>
</li><li class=" ">    <p>
TOTAL_CPU_TIME    </p>
</li><li class=" ">    <p>
CPU_TIME_PER_MESSAGE    </p>
</li><li class=" ">    <p>
MAXIMUM_CPU_TIME    </p>
</li><li class=" ">    <p>
MINIMUM_CPU_TIME    </p>
</li><li class=" ">    <p>
CPU_TIME_WAITING_FOR_INPUT_MESSAGE    </p>
</li><li class=" ">    <p>
ELAPSED_TIME_WAITING_FOR_INPUT_MESSAGE    </p>
</li><li class=" ">    <p>
TOTAL_INPUT_MESSAGES    </p>
</li><li class=" ">    <p>
TOTAL_SIZE_OF_INPUT_MESSAGES    </p>
</li><li class=" ">    <p>
MAX_SIZE_OF_INPUT_MESSAGES    </p>
</li><li class=" ">    <p>
MIN_SIZE_OF_INPUT_MESSAGES    </p>
</li><li class=" ">    <p>
NUM_THREADS_IN_POOL    </p>
</li><li class=" ">    <p>
TIMES_MAX_THREADS_REACHED    </p>
</li><li class=" ">    <p>
TOTAL_NUM_MQ_ERRORS    </p>
</li><li class=" ">    <p>
TOTAL_NUMBER_OF_MESSAGES_WITH_ERRRORS    </p>
</li><li class=" ">    <p>
TOTAL_NUMBER_OF_ERRORS_PROCESSING_MESSAGES    </p>
</li><li class=" ">    <p>
TOTAL_NUMBER_OF_TIMEOUTS_WAITING_FOR_REPLIES_TO_AGGREGATE_MESSAGES    </p>
</li><li class=" ">    <p>
TOTAL_NUMBER_OF_BACKOUTS    </p>
</li><li class=" ">    <p>
TOTAL_NUMBER_OF_COMMITS    </p>
</li></ul>    </div>
    <div class="section-2"  id="112462676_MessageFlowStatisticsMonitoringPlugin-Configuration"  >
        <h2>Configuration</h2>
    <p>
The plugin can be run on any collector. In order for this plugin to work, ensure that SYSTEM.ADMIN.SVRCONN type channel is created on the MQ Manager. This is the channel that the MQ Manager would publish the statistics information.    </p>
    <p>
For this monitor to work, ensure that the message flow statistics are enabled. To enable it, run the following command on the broker:    </p>
    <div class="confbox programlisting">
                <div class="content">
        <pre><code>mqsichangeflowstats BrokerName -s -g -j -n advanced -t basic -b basic -c active -o xml</code></pre>
        </div>
    </div>
    <p>
Restart the broker after executing the above command.    </p>
    <p>
For more information, go to<br/><a href="http://www-01.ibm.com/software/integration/wbimessagebroker/library">http://www-01.ibm.com/software/integration/wbimessagebroker/library</a>    </p>
    <p>
When configuring the monitor to run in the dynaTrace environment, use the following value for the entry Stats Subscription Topic:    </p>
    <div class="confbox programlisting">
                <div class="content">
        <pre><code>$SYS/Broker/+/StatisticsAccounting/SnapShot/#</code></pre>
        </div>
    </div>
    <p>
This monitor works for IBM Message Broker 7.0 and higher. Additionally, for this monitor to work in dynaTrace, version 4.2.0.3170 and higher is required.    </p>
    </div>
    <div class="section-2"  id="112462676_MessageFlowStatisticsMonitoringPlugin-Installation"  >
        <h2>Installation</h2>
    <p>
Import the Plugin into the dynaTrace Server. For details how to do this please refer to the <a href="https://community.dynatrace.com/community/display/DOCDT50/Manage+and+Develop+Plugins#ManageandDevelopPlugins-ManageandDevelopPlugins">dynaTrace  documentation</a>.    </p>
    </div>
            </div>
        </div>
        <div class="footer">
        </div>
    </div>
</body>
</html>