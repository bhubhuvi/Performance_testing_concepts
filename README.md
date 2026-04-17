<?xml version="1.0" encoding="UTF-8"?>
<jmeterTestPlan version="1.2" properties="5.0" jmeter="5.6.3">
  <hashTree>
    <TestPlan guiclass="TestPlanGui" testclass="TestPlan" testname="Test Plan-ModuleController">
      <elementProp name="TestPlan.user_defined_variables" elementType="Arguments" guiclass="ArgumentsPanel" testclass="Arguments" testname="User Defined Variables">
        <collectionProp name="Arguments.arguments"/>
      </elementProp>
    </TestPlan>
    <hashTree>
      <ThreadGroup guiclass="ThreadGroupGui" testclass="ThreadGroup" testname="Thread Group">
        <intProp name="ThreadGroup.num_threads">1</intProp>
        <intProp name="ThreadGroup.ramp_time">1</intProp>
        <boolProp name="ThreadGroup.same_user_on_next_iteration">true</boolProp>
        <stringProp name="ThreadGroup.on_sample_error">continue</stringProp>
        <elementProp name="ThreadGroup.main_controller" elementType="LoopController" guiclass="LoopControlPanel" testclass="LoopController" testname="Loop Controller">
          <stringProp name="LoopController.loops">1</stringProp>
          <boolProp name="LoopController.continue_forever">false</boolProp>
        </elementProp>
      </ThreadGroup>
      <hashTree>
        <ConfigTestElement guiclass="HttpDefaultsGui" testclass="ConfigTestElement" testname="HTTP Request Defaults">
          <stringProp name="HTTPSampler.domain">jpetstore.aspectran.com</stringProp>
          <stringProp name="HTTPSampler.protocol">https</stringProp>
          <elementProp name="HTTPsampler.Arguments" elementType="Arguments" guiclass="HTTPArgumentsPanel" testclass="Arguments" testname="User Defined Variables">
            <collectionProp name="Arguments.arguments"/>
          </elementProp>
          <stringProp name="HTTPSampler.implementation"></stringProp>
        </ConfigTestElement>
        <hashTree/>
        <GenericController guiclass="LogicControllerGui" testclass="GenericController" testname="Simple Controller-signin"/>
        <hashTree>
          <HTTPSamplerProxy guiclass="HttpTestSampleGui" testclass="HTTPSamplerProxy" testname="openpage" enabled="true">
            <stringProp name="HTTPSampler.path">/</stringProp>
            <boolProp name="HTTPSampler.follow_redirects">true</boolProp>
            <stringProp name="HTTPSampler.method">GET</stringProp>
            <boolProp name="HTTPSampler.use_keepalive">true</boolProp>
            <boolProp name="HTTPSampler.postBodyRaw">false</boolProp>
            <elementProp name="HTTPsampler.Arguments" elementType="Arguments" guiclass="HTTPArgumentsPanel" testclass="Arguments" testname="User Defined Variables">
              <collectionProp name="Arguments.arguments"/>
            </elementProp>
          </HTTPSamplerProxy>
          <hashTree/>
          <HTTPSamplerProxy guiclass="HttpTestSampleGui" testclass="HTTPSamplerProxy" testname="Signinpage" enabled="true">
            <stringProp name="HTTPSampler.path">/account/signonForm</stringProp>
            <boolProp name="HTTPSampler.follow_redirects">true</boolProp>
            <stringProp name="HTTPSampler.method">GET</stringProp>
            <boolProp name="HTTPSampler.use_keepalive">true</boolProp>
            <boolProp name="HTTPSampler.postBodyRaw">false</boolProp>
            <elementProp name="HTTPsampler.Arguments" elementType="Arguments" guiclass="HTTPArgumentsPanel" testclass="Arguments" testname="User Defined Variables">
              <collectionProp name="Arguments.arguments"/>
            </elementProp>
          </HTTPSamplerProxy>
          <hashTree/>
          <HTTPSamplerProxy guiclass="HttpTestSampleGui" testclass="HTTPSamplerProxy" testname="Signin_pass_user" enabled="true">
            <stringProp name="HTTPSampler.path">/account/signonForm</stringProp>
            <boolProp name="HTTPSampler.follow_redirects">true</boolProp>
            <stringProp name="HTTPSampler.method">GET</stringProp>
            <boolProp name="HTTPSampler.use_keepalive">true</boolProp>
            <boolProp name="HTTPSampler.postBodyRaw">false</boolProp>
            <elementProp name="HTTPsampler.Arguments" elementType="Arguments" guiclass="HTTPArgumentsPanel" testclass="Arguments" testname="User Defined Variables">
              <collectionProp name="Arguments.arguments">
                <elementProp name="password" elementType="HTTPArgument">
                  <boolProp name="HTTPArgument.always_encode">true</boolProp>
                  <stringProp name="Argument.value">j2ee</stringProp>
                  <stringProp name="Argument.metadata">=</stringProp>
                  <boolProp name="HTTPArgument.use_equals">true</boolProp>
                  <stringProp name="Argument.name">password</stringProp>
                </elementProp>
                <elementProp name="username" elementType="HTTPArgument">
                  <boolProp name="HTTPArgument.always_encode">true</boolProp>
                  <stringProp name="Argument.value">j2ee</stringProp>
                  <stringProp name="Argument.metadata">=</stringProp>
                  <boolProp name="HTTPArgument.use_equals">true</boolProp>
                  <stringProp name="Argument.name">username</stringProp>
                </elementProp>
                <elementProp name="signon" elementType="HTTPArgument">
                  <boolProp name="HTTPArgument.always_encode">true</boolProp>
                  <stringProp name="Argument.value">login</stringProp>
                  <stringProp name="Argument.metadata">=</stringProp>
                  <boolProp name="HTTPArgument.use_equals">true</boolProp>
                  <stringProp name="Argument.name">signon</stringProp>
                </elementProp>
              </collectionProp>
            </elementProp>
          </HTTPSamplerProxy>
          <hashTree/>
        </hashTree>
        <GenericController guiclass="LogicControllerGui" testclass="GenericController" testname="Simple Controller-fish"/>
        <hashTree>
          <ModuleController guiclass="ModuleControllerGui" testclass="ModuleController" testname="Module Controller">
            <collectionProp name="ModuleController.node_path">
              <stringProp name="-1412481124">Test Plan-ThroughputController</stringProp>
              <stringProp name="1173557342">Test Plan-ModuleController</stringProp>
              <stringProp name="-1948168983">Thread Group</stringProp>
              <stringProp name="2125856773">Simple Controller-signin</stringProp>
            </collectionProp>
          </ModuleController>
          <hashTree/>
          <HTTPSamplerProxy guiclass="HttpTestSampleGui" testclass="HTTPSamplerProxy" testname="Fish">
            <stringProp name="HTTPSampler.path">/categories/FISH</stringProp>
            <boolProp name="HTTPSampler.follow_redirects">true</boolProp>
            <stringProp name="HTTPSampler.method">GET</stringProp>
            <boolProp name="HTTPSampler.use_keepalive">true</boolProp>
            <boolProp name="HTTPSampler.postBodyRaw">false</boolProp>
            <elementProp name="HTTPsampler.Arguments" elementType="Arguments" guiclass="HTTPArgumentsPanel" testclass="Arguments" testname="User Defined Variables">
              <collectionProp name="Arguments.arguments">
                <elementProp name="viewCategory" elementType="HTTPArgument">
                  <boolProp name="HTTPArgument.always_encode">false</boolProp>
                  <stringProp name="Argument.value"></stringProp>
                  <stringProp name="Argument.metadata">=</stringProp>
                  <boolProp name="HTTPArgument.use_equals">true</boolProp>
                  <stringProp name="Argument.name">viewCategory</stringProp>
                </elementProp>
                <elementProp name="categoryId" elementType="HTTPArgument">
                  <boolProp name="HTTPArgument.always_encode">false</boolProp>
                  <stringProp name="Argument.value">Fish</stringProp>
                  <stringProp name="Argument.metadata">=</stringProp>
                  <boolProp name="HTTPArgument.use_equals">true</boolProp>
                  <stringProp name="Argument.name">categoryId</stringProp>
                </elementProp>
              </collectionProp>
            </elementProp>
          </HTTPSamplerProxy>
          <hashTree/>
        </hashTree>
        <GenericController guiclass="LogicControllerGui" testclass="GenericController" testname="Simple Controller-dog"/>
        <hashTree>
          <ModuleController guiclass="ModuleControllerGui" testclass="ModuleController" testname="Module Controller">
            <collectionProp name="ModuleController.node_path">
              <stringProp name="-1412481124">Test Plan-ThroughputController</stringProp>
              <stringProp name="1173557342">Test Plan-ModuleController</stringProp>
              <stringProp name="-1948168983">Thread Group</stringProp>
              <stringProp name="2125856773">Simple Controller-signin</stringProp>
            </collectionProp>
          </ModuleController>
          <hashTree/>
          <HTTPSamplerProxy guiclass="HttpTestSampleGui" testclass="HTTPSamplerProxy" testname="Dog">
            <stringProp name="HTTPSampler.path">/categories/DOG</stringProp>
            <boolProp name="HTTPSampler.follow_redirects">true</boolProp>
            <stringProp name="HTTPSampler.method">GET</stringProp>
            <boolProp name="HTTPSampler.use_keepalive">true</boolProp>
            <boolProp name="HTTPSampler.postBodyRaw">false</boolProp>
            <elementProp name="HTTPsampler.Arguments" elementType="Arguments" guiclass="HTTPArgumentsPanel" testclass="Arguments" testname="User Defined Variables">
              <collectionProp name="Arguments.arguments">
                <elementProp name="viewCategory" elementType="HTTPArgument">
                  <boolProp name="HTTPArgument.always_encode">false</boolProp>
                  <stringProp name="Argument.value"></stringProp>
                  <stringProp name="Argument.metadata">=</stringProp>
                  <boolProp name="HTTPArgument.use_equals">true</boolProp>
                  <stringProp name="Argument.name">viewCategory</stringProp>
                </elementProp>
                <elementProp name="categoryId" elementType="HTTPArgument">
                  <boolProp name="HTTPArgument.always_encode">false</boolProp>
                  <stringProp name="Argument.value">DOG</stringProp>
                  <stringProp name="Argument.metadata">=</stringProp>
                  <boolProp name="HTTPArgument.use_equals">true</boolProp>
                  <stringProp name="Argument.name">categoryId</stringProp>
                </elementProp>
              </collectionProp>
            </elementProp>
          </HTTPSamplerProxy>
          <hashTree/>
        </hashTree>
        <ResultCollector guiclass="ViewResultsFullVisualizer" testclass="ResultCollector" testname="View Results Tree">
          <boolProp name="ResultCollector.error_logging">false</boolProp>
          <objProp>
            <name>saveConfig</name>
            <value class="SampleSaveConfiguration">
              <time>true</time>
              <latency>true</latency>
              <timestamp>true</timestamp>
              <success>true</success>
              <label>true</label>
              <code>true</code>
              <message>true</message>
              <threadName>true</threadName>
              <dataType>true</dataType>
              <encoding>false</encoding>
              <assertions>true</assertions>
              <subresults>true</subresults>
              <responseData>false</responseData>
              <samplerData>false</samplerData>
              <xml>false</xml>
              <fieldNames>true</fieldNames>
              <responseHeaders>false</responseHeaders>
              <requestHeaders>false</requestHeaders>
              <responseDataOnError>false</responseDataOnError>
              <saveAssertionResultsFailureMessage>true</saveAssertionResultsFailureMessage>
              <assertionsResultsToSave>0</assertionsResultsToSave>
              <bytes>true</bytes>
              <sentBytes>true</sentBytes>
              <url>true</url>
              <threadCounts>true</threadCounts>
              <idleTime>true</idleTime>
              <connectTime>true</connectTime>
            </value>
          </objProp>
          <stringProp name="filename"></stringProp>
        </ResultCollector>
        <hashTree/>
      </hashTree>
    </hashTree>
  </hashTree>
</jmeterTestPlan>
