**Working lookup calculated col:** 

Option #1
```
MyLookup = 
VAR _x = thisTable[etd_vadovas_asm_id]
RETURN MINX(FILTER(lookupTable, lookupTable[asm_id] = _x), lookupTable[asm_pavadinimas])
```

Option #2
```
MyLookup = 
VAR _val = thisTable[etd_vadovas_asm_id]
RETURN CALCULATE ( LOOKUPVALUE(lookupTable[asm_pavadinimas], lookupTable[asm_id], _val),
                   ALLEXCEPT(thisTable, thisTable[etd_vadovas_asm_id]) )
```
------------------------------------------------------------------------------------------
