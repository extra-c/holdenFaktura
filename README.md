# holdenFaktura
Genom holdenFaktura kan du skapa egna fakturor <b>kostnadsfritt</b> och lätt genom en formulär.
För att komma igång kan du ladda upp form.html till din hemsida och köra.
Alternativt kan du besöka https://www.holden.se/api/
<code>
Fakturamall: https://www.holden.se/api/faktura/index.php?referens
</code>
<pre>demo</pre>
### Krav
Minst jQuery 1.11.1 <br>
Minst Bootstrap Javascript 3.3.0

## Kom igång
Inkludera detta innan ```</header>```
```
<!------ Krävs för API START INKLUDERA I HEADER ---------->
<script src="//code.jquery.com/jquery-1.11.1.min.js"></script><br>
<script src="https://www.holden.se/api/call.js"></script>
<!------ Krävs för API END ---------->
```
Använd dig av filen <b>form.html</b> eller följande formulär:
```
<form id="form" method="GET" target="_blank" action="https://www.holden.se/api/faktura/index.php">
        

		<h3>Faktura</h3>
	        <label>Referens/Nummer</label>
	        <input type="text" name="referens" class="form-control">

	 
	        <label>Faktuereringsdatum</label>
	        <input type="text" name="faktureringsdatum" class="form-control">
	    
	  
	        <label>Förfallodatum</label>
	        <input type="text" name="forfallodatum" class="form-control">


        
        <h3>Betalningsmottagare</h3>

            <label>Förnamn & Efternamn / Företag</label>
            <input type="text" name="tperson" class="form-control">
          
            <label>Org.nummer (Kan lämnas tom)</label>
            <input type="text" name="torgnummer" class="form-control">


            <label>Adress</label>
            <input type="text" name="tadress" class="form-control">

            <label>Postnummer</label>
            <input type="text" name="tpostnummer" class="form-control">

            <label>Stad</label>
            <input type="text" name="tstad" class="form-control">


            <label>Län</label>
            <input type="text" name="tlan" class="form-control">

            <label>Land</label>
            <input type="text" name="tland" class="form-control">

        <h3>Fakturamottagare</h3>

            <label>Förnamn & Efternamn / Företag</label>
            <input type="text" name="fperson" class="form-control">

            <label>Org.nummer (Kan lämnas tom)</label>
            <input type="text" name="forgnummer" class="form-control">


            <label>Adress</label>
            <input type="text" name="fadress" class="form-control">

            <label>Postnummer</label>
            <input type="text" name="fpostnummer" class="form-control">

            <label>Stad</label>
            <input type="text" name="fstad" class="form-control">

            <label>Län</label>
            <input type="text" name="flan" class="form-control">

            <label>Land</label>
            <input type="text" name="fland" class="form-control">


        <h3>Information</h3>


            <label>Status: (Exempel: Inte Betald, Betald, Försenad)</label>
            <input type="text" name="status" class="form-control">


            <label>Information & villkor</label>
            <textarea name="villkor" rows="5" class="form-control"></textarea>


      <table class="table table-bordered table-hover" id="tab_logic">
        <thead>
          <tr>
            <th class="text-center"> # </th>
            <th class="text-center"> Produkt </th>
            <th class="text-center"> Antal </th>
            <th class="text-center"> Startavgift </th>
            <th class="text-center"> Pris </th>
            <th class="text-center"> Totalt </th>
          </tr>
        </thead>
        <tbody>
          <tr id='addr0'>
            <td>1</td>
            <td><input type="text" name='product[]'  placeholder='Skriv produktnamn' class="form-control"/></td>
            <td><input type="number" name='qty[]' placeholder='Ange antal' class="form-control qty" step="0" min="0"/></td>
            <td><input type="number" name='startavgift[]' placeholder='Ange startavgift' class="form-control startavgift" step="0" min="0"/></td>
            <td><input type="number" name='price[]' placeholder='Ange styckpris' class="form-control price" step="0.00" min="0"/></td>
            <td><input type="number" name='total[]' placeholder='0.00' class="form-control total" readonly/></td>
          </tr>
          <tr id='addr1'></tr>
        </tbody>
      </table>
    </div>
</div>
  <div class="row clearfix">
    <div class="col-md-12">
      <button id="add_row" type=button class="btn btn-default pull-left">Lägg till rad</button>
      <button id='delete_row' type=button class="pull-right btn btn-default">Ta bort rad</button>
      
    </div>
  </div>
  <div class="row clearfix" style="margin-top:20px">
    <div class="pull-right col-md-4">
      <table class="table table-bordered table-hover" id="tab_logic_total">
        <tbody>
          <tr>
            <th class="text-center">Totalt exkl. moms</th>
            <td class="text-center"><input type="number" name='sub_total' placeholder='0.00' class="form-control" id="sub_total" readonly/></td>
          </tr>
          <tr>
            <th class="text-center">Momssats</th>
            <td class="text-center"><div class="input-group mb-2 mb-sm-0">
                <input type="number" class="form-control" id="tax" name="tax_procent" placeholder="0">
                <div class="input-group-addon">%</div>
              </div></td>
          </tr>
          <tr>
            <th class="text-center">Moms</th>
            <td class="text-center"><input type="number" name='tax_amount' id="tax_amount" placeholder='0.00' class="form-control" readonly/></td>
          </tr>
          <tr>
            <th class="text-center">Totalt</th>
            <td class="text-center"><input type="number" name='total_amount' id="total_amount" placeholder='0.00' class="form-control" readonly/></td>
          </tr>
        </tbody>
      </table>
      <input type="submit" id="submit" class="btn btn-success pull-right col-md-12" value="Skapa Faktura">
    </form>
```

## Buggar
Inga kända buggar. Kolla mer här: https://github.com/extra-c/holdenFaktura/issues
