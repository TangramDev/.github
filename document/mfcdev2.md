<div align=center>

# Developing MFC Desktop Application with Web Runtime
  
<div align=center id="MfcApp"><img src="https://user-images.githubusercontent.com/26355688/178436304-730ede1e-23c1-4bc9-b94b-4b082dc3e7ab.jpg" width="75%" height="100%"/></div>
<div align=center>

## MFC Development of WebRuntime Applications <br>need to pay attention to the following aspects：
  
</div>
<div align=left>
<ol>
<li>correctly process the "manifest configuration" of the MFC project</li>
<li>configure the compilation options correctly(WebRuntime only supports 64-bit applications).</li>
<li>AppBase: Replace CWinApp(Ex) with CWebRTApp(Ex)</li>
<li>Tabbed MDI Application: Tabbed MDIFrame Window
<ol>
<li>The Base Class of Tabbed MDIFrame Window: Replace CMDIFrameWndEx with CWebRTMDIFrame</li>
<li>The Message Map of Tabbed MDIFrame Window: Replace CMDIFrameWndEx with CWebRTMDIFrame</li>
</ol>
</li>
<li>FormView: Delete the Call to ResizeParentToFit()</li>
<li>Serialization</li>
<li>Dialog Application: the Function "InitInstance" of App Class should return true</li>
</ol>  
</div>
  
<div align=center>
<hr />  
  
## (1)Preparation: This step is required <br>_for all types of MFC Desktop Applications_

<div align=center><img src="https://user-images.githubusercontent.com/26355688/178430601-581d57a3-652b-4781-8da5-d1256c4f89b9.gif" width="100%" height="100%"/></div>
<hr />

## (2)AppBase: Replace CWinApp(Ex) with CWebRTApp(Ex), <br>_This step is required for all types of MFC Desktop Applications_<div align=center id ="MFCAppDev_AppBase"><img src="https://user-images.githubusercontent.com/26355688/178430698-1bd5c36b-3828-41b1-807d-5f441d6902f6.gif" width="100%" height="100%"/></div>
### More information:
  
| _MFC Application Type_       | _description_                                                                                                    |
| -- | ---------------------------------------------------------------------------------------------------------------- |
|  <div align=center>**If your app is an MFC Dialog Type Application**</div> |&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;  <div align=center><img src="https://media1.giphy.com/media/UGd99qfyY5XjvHhAXZ/giphy.gif?cid=790b76114983d155a4cdbee5f9903e16261bce4fba81c188&rid=giphy.gif&ct=g" width="100%"/></div>|
| <div align=center>**If your MFC application is an _SDI_, _MDT_ or _Standard MFC MDI_ style Desktop Application**</div>|<div align=center>_If there is no CFormView or CFormView derived classes in your MFC application, as long as the replacement of the App class base class is completed, the C++ code part required by WebRuntime has been completed. If it contains CFormView or CFormView derived classes, please refer to the following CFormView section. If the application supports the Doc/View architecture, the document serialization please refers to the following serialization section._</dv>|  
 
<hr />
  
<div align=center>
  
## (3)Tabbed MDI Application: <br>_Tabbed Main Frame Window and its Message Map_ 
  
| _Tabbed MDI Frame Window_       | _description_                                                                                                    |
| -- | ---------------------------------------------------------------------------------------------------------------- |
|  <div align=center>Replace Base Class CMDIFrameWndEx <br>with CWebRTMDIFrame</div> |&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;  <div align=center id ="MFCAppDev_MDIFrame"><img src="https://user-images.githubusercontent.com/26355688/178430840-f0145e7e-b7f1-418a-82f2-e7a3fe172dcd.gif" width="100%" height="100%"/></div>                          |
| <div align=center>Tabbed MDI Frame Window <br>Message Map: Replace CMDIFrameWndEx <br>with CWebRTMDIFrame</div>|<div align=center id ="MFCAppDev_MsgLoop"><img src="https://user-images.githubusercontent.com/26355688/178400063-e23e474d-0127-43fe-95b5-c1ce724b4ee8.gif" width="100%" height="100%"/></div></div>                    |
  
<hr />

## (4)CFormView: <br>Delete the Call to ResizeParentToFit()

<div align=center id ="MFCAppDev_FormView"><img src="https://user-images.githubusercontent.com/26355688/178399844-1678d591-160b-46ec-b2b8-c17711c88c4a.gif" width="100%" height="100%"/></div>
<hr />

## (5)Serialization

<div align=center id ="MFCAppDev_Serialization"><img src="https://user-images.githubusercontent.com/26355688/178399660-91de2238-936b-4ac6-bb44-c4f41f641cb6.gif" width="100%" height="100%"/></div>
<hr />
