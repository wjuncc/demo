---
layout: post
title:  "script router react"
date:   2017-10-24 08:42:42 +0800
categories:  
tags: 
    - react
    - router


---

# sourece code #

Build.as

```actionscript
package  
{
	import wj7.utils.LM;
	import wj7.utils.uFD;
	import wj7.utils.uFile;
	import wj7.utils.uNow;
	/**
pathIN = ur"E:/n/learn/react/router/lessons/v66/acp/Build.as"
pathOUT = ur"E:/n/learn/react/router/lessons/v66/acp____/Build.py"
	
	 * ...
	 * @author wj
	 * run
	 */
	public class Build 
	{ 
		public function Build() 
		{
			this.doMain();
		} 
		
		public function doMain():void 
		{
			var demoPath:String = uFD.ProjectDir("demo.markdown");
			var demoTxt:String = uNow.read_fast_return(demoPath);
			
			//LM.alert("123");
			var lnArr:Array = [];
			
			var p:String = ur"E:\n\learn\react\router\lessons"
			var arr:Array = uFile.loop_dirV4(p, "README.md",2);
			for (var i:int = 0; i < arr.length; i++) 
			{
				var p:String = arr[i];  
				//trace(p);
				trace(p);
				lnArr.push(p);
			}
			
			var lnTxt:String = lnArr.join("\r\n");   
			
			//LM.alert(lnTxt);     
			
			LM.alert(demo);
			 
		} 
	}

	function main(){		
		Build();
	}
}
```

#### 参考 ####

