﻿<div align="center">

## Background/foreground color changer


</div>

### Description

This is a little javascript that allows you to change the color of the background and the foreground colors on a webpage. It can be used in different ways. I hope you all like it.
 
### More Info
 


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[masterp](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/masterp.md)
**Level**          |Intermediate
**User Rating**    |3.7 (59 globes from 16 users)
**Compatibility**  |
**Category**       |[Internet/ Browsers/ HTML](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/internet-browsers-html__2-68.md)
**World**          |[Java](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/java.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/masterp-background-foreground-color-changer__2-2695/archive/master.zip)





### Source Code

```
<html>
<HEAD>
<SCRIPT LANGUAGE="JavaScript">
<!-- Begin
  redValue = 255;
  blueValue = 255;
  greenValue = 255;
  redForeValue = 0;
  blueForeValue = 0;
  greenForeValue = 0;
  maxValue = 255;
  hexValues = new Array("0","1","2","3","4","5","6","7","8","9","A","B","C","D","E","F");
  i = 0;
  function toHex(integer)
  {
   hexDigit1 = Math.floor(integer / 16);
   hexDigit2 = (integer % 16);
   return hexValues[hexDigit1] + hexValues[hexDigit2];
  }
  function shiftFG()
  {
   redFGHex = toHex(redForeValue);
   blueFGHex = toHex(blueForeValue);
   greenFGHex = toHex(greenForeValue);
   bigFGHex = redFGHex + greenFGHex + blueFGHex;
   document.fgColor = bigFGHex;
   document.Interface.fgHex.value = bigFGHex;
   document.Interface.redFG.value = redForeValue;
   document.Interface.blueFG.value = blueForeValue;
   document.Interface.greenFG.value = greenForeValue;
  }
  function shiftBG()
  {
   redHex = toHex(redValue);
   blueHex = toHex(blueValue);
   greenHex = toHex(greenValue);
   bigHex = redHex + greenHex + blueHex;
   document.bgColor = bigHex;
   document.Interface.bgHex.value = bigHex;
   document.Interface.red.value = redValue;
   document.Interface.blue.value = blueValue;
   document.Interface.green.value = greenValue;
  }
  function incrementRed(isBackground)
  {
   if (isBackground == true )
   {
     redValue = redValue + 8;
     if (redValue > maxValue)
    {
      redValue = 0;
    }
     shiftBG();
   }
   if (isBackground == false)
   {
     redForeValue = redForeValue + 8;
     if (redForeValue > maxValue)
     {
      redForeValue = 0;
     }
     shiftFG();
   }
  }
  function decrementRed(isBackground)
  {
   if (isBackground == true)
   {
     redValue = redValue - 8;
     if (redValue < 0 )
     {
      redValue = 255;
     }
     shiftBG();
   }
   else
   {
     redForeValue = redForeValue - 8;
     if (redForeValue < 0)
     {
      redForeValue = 255;
     }
     shiftFG();
   }
  }
  function setRed(value, isBackground)
  {
   if(value > -1 && value < 256)
   {
     if( isBackground == true )
     {
      redValue = value;
      shiftBG();
     }
     else
     {
      redForeValue = value;
      shiftFG();
     }
   }
  }
  function incrementBlue(isBackground)
  {
   if ( isBackground == true )
   {
     blueValue = blueValue + 8;
     if (blueValue > maxValue)
     {
      blueValue = 0;
     }
     shiftBG();
   }
   else
   {
     blueForeValue = blueForeValue + 8;
     if ( blueForeValue > maxValue )
     {
      blueForeValue = 0;
     }
     shiftFG();
   }
  }
  function decrementBlue(isBackground)
  {
   if (isBackground == true)
   {
     blueValue = blueValue - 8;
     if (blueValue < 0)
     {
      blueValue = 255;
     }
     shiftBG();
   }
   else
   {
     blueForeValue = blueForeValue - 8;
     if (blueForeValue < 0)
     {
      blueForeValue = 255;
     }
     shiftFG();
   }
  }
  function setBlue(value, isBackground)
  {
   if (value > -1 && value < 256)
   {
     if ( isBackground == true )
     {
      blueValue = value;
      shiftBG();
     }
     else
     {
      blueForeValue = value;
      shiftFG();
     }
   }
  }
  function incrementGreen(isBackground)
  {
   if (isBackground == true)
   {
     greenValue = greenValue + 8;
     if (greenValue > maxValue)
     {
      greenValue = 0;
     }
     shiftBG();
   }
   else
   {
     greenForeValue = greenForeValue + 8;
     if (greenForeValue > maxValue)
     {
      greenForeValue = 0;
     }
     shiftFG();
   }
  }
  function decrementGreen(isBackground)
  {
   if (isBackground == true)
   {
     greenValue = greenValue - 8;
     if (greenValue < 0 )
     {
      greenValue = 255;
     }
     shiftBG();
   }
   else
   {
     greenForeValue = greenForeValue - 8;
     if (greenForeValue < 0)
     {
      greenForeValue = 255;
     }
     shiftFG();
   }
  }
  function setGreen(value, isBackground)
  {
   if ( value > -1 && value < 256 )
   {
     if ( isBackground == true )
     {
      greenValue = value;
      shiftBG();
     }
     else
     {
      greenForeValue = value;
      shiftFG();
     }
   }
  }
  function unHex(string, fgbg)
  {
   hex = string.toUpperCase();
   counter = 0;
   while (hex.charAt(0) != hexValues[counter])
   {
     counter++;
   }
   r = 16 * counter;
   counter = 0;
   while (hex.charAt(1) != hexValues[counter])
   {
     counter++;
   }
   r = r + counter;
   counter = 0;
   while (hex.charAt(2) != hexValues[counter])
   {
     counter++;
   }
   g = 16 * counter;
   counter = 0;
   while (hex.charAt(3) != hexValues[counter])
   {
     counter++;
   }
   g = g + counter;
   counter = 0;
   while (hex.charAt(4) != hexValues[counter])
   {
     counter++;
   }
   b = 16 * counter;
   counter = 0;
   while (hex.charAt(5) != hexValues[counter])
   {
     counter++;
   }
   b = b + counter;
   if (fgbg == "bg")
   {
     redValue = r;
     blueValue = b;
     greenValue = g;
     document.Interface.red.value = redValue;
     document.Interface.blue.value = blueValue;
     document.Interface.green.value = greenValue;
   }
   if (fgbg == "fg")
   {
     redForeValue = r;
     blueForeValue = b;
     greenForeValue = g;
     document.Interface.redFG.value = redForeValue;
     document.Interface.blueFG.value = blueForeValue;
     document.Interface.greenFG.value = greenForeValue;
   }
  }
  function validChar(char)
  {
   for (j = 0; j < hexValues.length; j++)
   {
     if (char == hexValues[j])
     {
      return true;
     }
   }
   return false;
  }
  function isHex(string)
  {
   if (string.length != 6)
   {
     return false;
   }
   for (k = 0; k < 6; k++)
   {
     if (! validChar(string.charAt(k)))
     {
      return false;
     }
   }
   return true;
  }
  function setBGHex(value)
  {
   if (isHex(value.toUpperCase()))
   {
     document.bgColor = value;
     unHex(value, "bg");
   }
  }
  function setFGHex(value)
  {
   if (isHex(value.toUpperCase()))
   {
     document.fgColor = value;
     unHex(value, "fg");
   }
  }
// End -->
</script>
<style>
  input
  {
   font-family: Arial, Verdana, sans serif;
   font-size: 15px;
   border: 1px inset black
  }
 .button
  {
   font-family: MS sans serif;
   font-size: 15px;
   border: 1px inset black;
   background: #000099;
   color: #FFFFFF;
   font-weight: bold
  }
</style>
</HEAD>
<BODY bgcolor=ffffff topmargin=12 leftmargin=2 rightmargin=2>
<center>
<form name=Interface>
<table border=1 cellspacing=0 cellpadding=5 bordercolordark="ffffff" bordercolorlight="000000" bgcolor="cccccc">
  <tr>
   <td colspan=3 align=center>Background</td>
   <td><input type=text name=bgHex onKeyup="setBGHex(this.value)"></td>
   <td colspan=2 align=center>Foreground</td>
   <td><input type=text name=fgHex onKeyup="setFGHex(this.value)"></td>
  </tr>
  <tr>
   <td>Red</td>
   <td><input type=button value=" + " onClick="incrementRed(true)"></td>
   <td><input type=button value=" - " onClick="decrementRed(true)"></td>
   <td><input type=text name="red" onKeyup="setRed(this.value, true)"></td>
   <td><input type=button value=" + " onClick="incrementRed(false)"></td>
   <td><input type=button value=" - " onClick="decrementRed(false)"></td>
   <td><input type=text name=redFG onKeyup="setRed(this.value, false)"></td>
  </tr>
  <tr>
   <td>Green</td>
   <td><input type=button value=" + " onClick="incrementGreen(true)"></td>
   <td><input type=button value=" - " onClick="decrementGreen(true)"></td>
   <td><input type=text name="green" onKeyup="setGreen(this.value, true)"></td>
   <td><input type=button value=" + " onClick="incrementGreen(false)"></td>
   <td><input type=button value=" - " onClick="decrementGreen(false)"></td>
   <td><input type=text name=greenFG onKeyup="setGreen(this.value, false)"></td>
  </tr>
  <tr>
   <td>Blue</td>
   <td><input type=button value=" + " onClick="incrementBlue(true)"></td>
   <td><input type=button value=" - " onClick="decrementBlue(true)"></td>
   <td><input type=text name="blue" onKeyup="setBlue(this.value, true)"></td>
   <td><input type=button value=" + " onClick="incrementBlue(false)"></td>
   <td><input type=button value=" - " onClick="decrementBlue(false)"></td>
   <td><input type=text name=blueFG onKeyup="setBlue(this.value, false)"></td>
  </tr>
</table>
</form>
</center>
</body>
</head>
```

