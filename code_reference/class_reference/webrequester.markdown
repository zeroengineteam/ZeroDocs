 `Component` `Networking`



(NOTE) A component we can use to facilitate web requests.

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
|[ Clear](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/webrequester.markdown#clear-void)|[ Url](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/webrequester.markdown#url-zero-engine-document)|[component](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/component.markdown)| |
|[ Run](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/webrequester.markdown#run-void)| | | |
|[ SetHeader](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/webrequester.markdown#setheader-void)| | | |
|[ SetPostData](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/webrequester.markdown#setpostdata-void)| | | |
|[ Constructor](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/webrequester.markdown#webrequester-void)| | | |


 #  Properties


---  
 #  Url : [string](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/string.markdown)

> Get and set the url that we make requests to.
> ``` lang=cpp, name=Zilch
> var Url : String


---  
 #  Methods


---  
 #  Clear : Void

> Clear headers and post data.
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function Clear()
> ``` 


---  
 #  Run : Void

> Run the web request (we should get data back in a WebResponse event).
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function Run()
> ``` 


---  
 #  SetHeader : Void

> Add a header to the web request .
> |Name|Type|Description|
> |---|---|---|
> |name|[string](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/string.markdown)| |
> |data|[string](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/string.markdown)| |
> ``` lang=cpp, name=Zilch
> function SetHeader(name : String, data : String)
> ``` 


---  
 #  SetPostData : Void

> Add Post data to the request, this will also change the request to a post request.
> |Name|Type|Description|
> |---|---|---|
> |data|[string](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/string.markdown)| |
> ``` lang=cpp, name=Zilch
> function SetPostData(data : String)
> ``` 


---  
 #  WebRequester : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function WebRequester()
> ``` 


---  
 

 