# GrowtopiaItemDatabase
This is a database for the game Growtopia containing most recipes and core data, easily usable for developers.
Feel free to open an issue if some of the data is wrong, or pull request if you have additional data you could add.

## Note
This database was created by Nenkaai on the Growtopia Forums, Nenkai#4915. 
Some of the data is taken from the forums, 95% of the recipes is written by me.
The descriptions are originally taken from awesome187, and updated/fixed by me.

This project is licensed CC-BY-4.0, meaning you **must** provide credits before usage.

## Raw to JSON
A C# Project converting the data to JSON is included and compiled for Windows (you can download in the releases tab.) For other operating systems, .NET Core SDK 2.1 is required.

# Parsing example in C#

```csharp
using System;
using System.IO;

public class MyDataParser 
{
    public static Dictionary<int, ItemData > ItemList = new Dictionary<int, ItemData>();
    
    public static void Main(string[] args) 
    {
	ParseItemNames();
	Console.WriteLine(ItemList[0].ItemName); // Should print "Blank"
        Console.ReadKey();
    }
	
    public static void ParseItemNames() 
    {
	foreach (var j in File.ReadAllLines("CoreData.txt")))
	{
	    if (String.IsNullOrEmpty(j) || j.StartsWith("//")) continue;

	    string[] str = j.Split('|');
	    int id = Convert.ToInt32(str[0]);
	    string itemName = str[1];
	    var item = new ItemData();
	    item.ItemName = str[1];
	    ItemDesc[id] = item;
	}
    }
}

public class ItemData 
{
    public string ItemName { get; set; }
}  
```


