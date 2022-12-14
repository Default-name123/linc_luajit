# How install
* step one `haxelib remove linc_luajit`
* step two `haxelib git linc_luajit https://github.com/Default-name123/linc_luajit`
* done

# Forgot to say
* you don't need to compile with -D NO_PRECOMPILED_HEADERS for android targets build anymore, just use usual -release or -debug


## linc/LuaJIT
Haxe/hxcpp @:native bindings for [LuaJIT](http://luajit.org/).

This is a [linc](http://snowkit.github.io/linc/) library.

---

This library works with the Haxe cpp target only.

---

### Example usage

See test/Test.hx

Be sure to read the Lua documentation  
www.lua.org/manual/5.1/manual.html  

```haxe
import llua.Lua;
import llua.LuaL;
import llua.State;

class Test {
        
    static function main() {

        var lua:State = LuaL.newstate();
        LuaL.openlibs(lua);
        trace("Lua version: " + Lua.version());
        trace("LuaJIT version: " + Lua.versionJIT());

        LuaL.dofile(lua, "script.lua");

        Lua.getglobal(lua, "foo");

        Lua.pushinteger(lua, 1);
        Lua.pushnumber(lua, 2.0);
        Lua.pushstring(lua, "three");

        Lua.pcall(lua, 3, 0, 1);

        Lua.close(lua);
        
    }

}
```
