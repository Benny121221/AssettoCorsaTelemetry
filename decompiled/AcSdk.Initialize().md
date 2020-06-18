```cs
nop
if([AcSdk]AcSdk.AcSdk::this._initialized == null)
	return 1;

nop // L_0012
try
{
	//These are virtual method calls (callvirt)
	//The ldarg.0 and callvirts are simplified into their C# syntax
	this._physicsReader.Initialilize();
	this._graphicsReader.Initialize();
	this._staticReader.Initialize();
	nop
	this._initialized = 1;
	ldarg.0 //this
	this._connectionStatus = 1;
	stloc.0 //L_0049
}
catch([mscorlib]System.IO.FileNotFoundException)
{ //L_0049 to L_004F
	return 0;
}
catch([mscorlib]System.Exception)
{ //L_004F to L_005A
	this._connectionStatus = 3; // This is an enum, 3 corresponds to Error
	rethrow //There is a note in the readme about the rethrow opcode
}


return 1;
```
