<?xml version="1.0"?>
<t t-name="l10n_mn_freight.report_mn_account_invoice_data_new">
        	<t t-call="web.external_layout">
			<!--<t t-set="o" t-value="o.with_context({'lang':o.partner_id.lang})"/>-->
                <div class="page" style="font-family: Times New Roman, Times, serif; padding-top:10%; padding-right:4%; padding-left:4%;"> 
<!-- Дээд хар зураас -->
<div style="width:100%; height:4px; background-color:#1a1a1a; margin-bottom:5px; "/>

<!-- Лого ба гарчиг -->
<table style="width: 100%; font-size:15px; border-collapse: collapse;">
    <tr>
        <!-- Лого -->
        <td style="width: 50%; padding:5px; text-align:left;">
            <img t-attf-src="data:image/jpg;base64,{{o.company_id.logo}}" style="width:200px; height:60px;"/>
        </td>
        <!-- Гарчиг -->
        <td style="width: 50%; padding:5px; text-align:right; vertical-align: middle;">
            <p style="font-size: 36px; font-weight:bold; margin:0;">Төлбөрийн нэхэмжлэх</p>
        </td>
    </tr>
</table>

<!-- Доод улбар шар зураас -->
<div style="width:100%; height:4px; background-color:#f4821f; margin-top:5px; margin-bottom: 2%;"/>

                	
					<table style="width: 100%;">
						<tr>
							<td style="width: 45%;  font-size:15px; padding-right:30px;" rowspan="5"><b>Хаяг:</b> <t t-esc="o.company_id.street"/> </td>
							<td style="width: 25%;  font-size:15px;"><b>Нэхэмжлэхийн дугаар: </b></td>
							<td style="width: 20%;  font-size:15px; text-align:right;"><t t-esc="o.freight_id.name"/></td>
						</tr>
						<tr>
							<td style=" font-size:15px;"><b>Нэхэмжилсэн огноо: </b></td>
							<td style="font-size:15px; text-align:right;"><t t-esc="o.invoice_date"/></td>
						</tr>
						<tr>
							<td style=" font-size:15px;"><b>Төлбөр хийгдэх огноо: </b></td>
							<td style="font-size:15px; text-align:right;"><t t-esc="o.invoice_date_due"/></td>
						</tr>
						<tr>
							<td style="font-size:15px;"><b>Төлөгч:</b></td>
							<td style="font-size:15px; text-align:right;">
								<t t-if="o.partner_id.parent_id">
									<t t-esc="o.partner_id.parent_id.name"/>
								</t>
								<t t-if="not o.partner_id.parent_id">
									<t t-esc="o.partner_id.name"/>
								</t>
							</td>
						</tr>
						<tr>
							<td style="font-size:15px;"><b>Регистр: </b></td>
							<td style="font-size:15px; text-align:right;"><t t-esc="o.partner_id.vat"/></td>
						</tr>
						
					</table>
					<p style="font-size:15px; margin:0;"><b>Имэйл:</b> <t t-esc="o.company_id.email"/></p>
					<p style="margin:0; font-size:15px; text-align: left;"><b>Чингэлэг дугаар: </b><t t-esc="o.freight_id.container_num or ''"/> <t t-esc="o.freight_id.wagon_number or ''"/> 
																								<t t-esc="o.freight_id.truck_number or ''"/> <t t-esc="o.freight_id.airway_bill or ''"/></p>
					<p style="margin:0; font-size:15px; text-align: left;"><b>Ачааны мэдээлэл:</b> <t t-foreach="o.freight_id.operation_line_ids" t-as="line">
						
                		<span t-esc="line.product_id.name"/> 
                		<t t-if="line.cbm!=0">
							<span t-esc="line.cbm"/> 
						</t>
						<t t-if="line.packages!=0">
						 	<span t-esc="line.packages"/>
						</t>
						<t t-if="line.height!=0">
						   <span t-esc="line.height"/>
						</t>
						  <t t-if="line.weight!=0">
							<span t-esc="line.weight"/>
						  </t>
                		</t>
                	</p>
					<p style="margin:0; font-size:15px; text-align: left;"><b>Чингэлэг хэмжээ: </b><t t-esc="o.freight_id.container_id.name"/></p>
					<p style="margin:0; font-size:15px; text-align: left;margin-bottom: 2%;"><b>Илгээгч: </b><t t-esc="o.freight_id.supplier_id.name"/></p>
                	
                	<table style="width: 100%; font-size:15px;text-align: center; border-collapse: collapse; border: 1px solid black;">
    <tr class="border-black">
        <td rowspan="2" style="padding: 3px; width: 5%; border: 1px solid black; font-weight: bold; background-color:lightGray; text-align: center;">№</td>
        <td rowspan="2" style="padding: 3px; width: 45%; border: 1px solid black; font-weight: bold;background-color:lightGray; text-align: center;">Гүйлгээний утга</td>
        <td rowspan="2" style="padding: 3px; width: 10%; border: 1px solid black; font-weight: bold;background-color:lightGray;text-align: center;">Тоо</td>
        <td colspan="2" style="padding: 3px; width: 15%; border: 1px solid black; font-weight: bold;background-color:lightGray;text-align: center;">Нэгж үнэ</td>
        <td rowspan="2" style="padding: 3px; width: 10%; border: 1px solid black; font-weight: bold;background-color:lightGray;text-align: center;">Ханш</td>
        <td rowspan="2" style="padding: 3px; width: 15%; border: 1px solid black; font-weight: bold;background-color:lightGray;text-align: center;">Нийт үнэ</td>
    </tr>
    <tr class="border-black">
        <td style="padding: 3px; border: 1px solid black; font-weight: bold;background-color:lightGray;text-align: center;">Валют</td>
        <td style="padding: 3px; border: 1px solid black; font-weight: bold;background-color:lightGray;text-align: center;">Дүн</td>
    </tr>

    <t t-set="i" t-value="1"/>
    <tr class="border-black" t-foreach="o.invoice_line_ids" t-as="line">
        <td style="padding: 5px; border: 1px solid black;  text-align: center;">  <span t-esc="i"/> </td>
        <td style="padding: 5px; border: 1px solid black;  text-align: left;">
            <t t-esc="line.name"/>
        </td>
        <td style="padding: 5px; border: 1px solid black;  text-align: center;"> <span t-esc="round(line.quantity,2)"/></td>
        <td style="padding: 5px; border: 1px solid black;  text-align: right;"> <span t-field="line.sale_currency_id.name"/> </td>

        <t t-if="line.amount_local &gt; 0">
        	<td style="padding: 5px; border: 1px solid black;  text-align: right;">  <span t-esc="round(line.amount_local/line.currency_rate,2)"/></td>
        	<td style="padding: 5px; border: 1px solid black;  text-align: right;"> <span t-field="line.currency_rate"/></td>
        	<td style="padding: 5px; border: 1px solid black;  text-align: right;"> <span t-esc="round(line.amount_local * line.quantity, 2)" t-options="{&quot;widget&quot;: &quot;float&quot;, &quot;precision&quot;: 2}"/></td>
        </t>
        <t t-if="line.amount_global &gt; 0">
       	 	<td style="padding: 5px; border: 1px solid black;  text-align: right;">  <span t-esc="round(line.amount_global,2)"/></td>
        	<td style="padding: 5px; border: 1px solid black;  text-align: right;"> <span t-field="line.currency_rate"/></td>
        	<td style="padding: 5px; border: 1px solid black;  text-align: right;"> <span t-esc="round(line.amount_global * line.quantity, 2)" t-options="{&quot;widget&quot;: &quot;float&quot;, &quot;precision&quot;: 2}"/></td>
        </t>
        <t t-set="i" t-value="i+1"/>
    </tr>

    <!-- НӨАТ -->
    <tr class="border-black">
        <td colspan="6" style="padding: 3px; border: 1px solid black; text-align: center; font-weight: bold;">НӨАТ</td>
        <td style="padding: 3px; border: 1px solid black; text-align: right;"> <span t-field="o.amount_tax_signed"/></td>
    </tr>

    <!-- Нийт дотоод тээвэр -->
    <tr class="border-black">
        <td colspan="6" style="padding: 3px; border: 1px solid black; text-align: left; font-weight: bold;">Нийт дотоод тээвэр</td>
        <td style="padding: 3px; border: 1px solid black; text-align: right;"> <span t-field="o.amount_total_local"/></td>
    </tr>
    
        <!-- Төлбөрийн нийт дүн -->
    <tr class="border-black">
        <td colspan="7" style="padding: 3px; border: 1px solid black; text-align: left; font-weight: bold;background-color:lightGray;">Төлбөрийн нийт дүн</td>
    </tr>

    <!-- Дотоод зайн нийт төлбөр -->
    <tr class="border-black">
        <td colspan="5" style="padding: 3px; border: 1px solid black; text-align: left; font-weight: bold;">Дотоод зайн нийт төлбөр</td>
        <td style="padding: 3px; border: 1px solid black;">MNT</td>
        <td style="padding:3px; border: 1px solid black; text-align: right; font-weight: bold;"> <span t-field="o.amount_total_local"/></td>
    </tr>
    
    <!-- Гадаад зайн нийт төлбөр -->
    <tr class="border-black">
        <td colspan="5" style="padding: 3px; border: 1px solid black; text-align: left; font-weight: bold;">Гадаад зайн нийт төлбөр</td>
        <td style="padding: 3px; border: 1px solid black;"><span t-field="o.sale_currency_id.name"/></td>
        <td style="padding:3px; border: 1px solid black; text-align: right; font-weight: bold;"> <span t-field="o.amount_total_global"/></td>
    </tr>
</table>


                	<br/>
                	<table style="width: 100%; font-size:15px;text-align: center; border-collapse: collapse; border: 1px solid black;">
                		
                			<tr class="border-black">
                				<td style="padding: 2px; width: 10%; border: 1px solid black; font-weight: bold; color:#fff; background-color:#3B3B3B">Валют</td>
                				<td style="padding: 2px; width: 20%; border: 1px solid black; font-weight: bold; color:#fff; background-color:#3B3B3B">Хас банк</td>
                				<td style="padding: 2px; width: 30%; border: 1px solid black; font-weight: bold; color:#fff; background-color:#3B3B3B">М банк</td>
                				<td style="padding: 2px; width: 20%; border: 1px solid black; font-weight: bold; color:#fff; background-color:#3B3B3B">Хаан банк</td>
                			</tr>
                			<tr>
                				<td style="padding: 2px; border: 1px solid black; width: 10%;  text-align: center; font-weight: bold;">MNT</td>
                				<td style="padding: 2px; border: 1px solid black; width: 10%;  text-align: center; ">MN53 0032 00 5005822382</td>
                				<td style="padding: 2px; border: 1px solid black; width: 10%;  text-align: center; ">MN67 0039 00 9310000064</td>
                				<td style="padding: 2px; border: 1px solid black; width: 10%;  text-align: center; ">MN53 0005 00 5038161107</td>
                			</tr>
							<tr>
                				<td style="padding: 2px; border: 1px solid black; width: 10%;  text-align: center; font-weight: bold;">USD</td>
                				<td style="padding: 2px; border: 1px solid black; width: 10%;  text-align: center; ">MN96 0032 00 5005822384</td>
                				<td style="padding: 2px; border: 1px solid black; width: 10%;  text-align: center; "/>
                				<td style="padding: 2px; border: 1px solid black; width: 10%;  text-align: center; ">MN29 0005 00 5038168523</td>
                			</tr>
							<tr>
                				<td style="padding: 2px; border: 1px solid black; width: 10%;  text-align: center; font-weight: bold;">EUR</td>
                				<td style="padding: 2px; border: 1px solid black; width: 10%;  text-align: center; ">MN95 0032 00 5005904076</td>
                				<td style="padding: 2px; border: 1px solid black; width: 10%;  text-align: center; "/>
                				<td style="padding: 2px; border: 1px solid black; width: 10%;  text-align: center; ">MN17 0005 00 5038168545</td>
                			</tr>
							<tr>
                				<td style="padding: 2px; border: 1px solid black; width: 10%;  text-align: center; font-weight: bold;">CNY</td>
                				<td style="padding: 2px; border: 1px solid black; width: 10%;  text-align: center; ">MN25 0032 00 5005904075</td>
                				<td style="padding: 2px; border: 1px solid black; width: 10%;  text-align: center; "/>
                				<td style="padding: 2px; border: 1px solid black; width: 10%;  text-align: center; ">MN23 0005 00 5038168534</td>
                			</tr>
                		
                	</table>
                	<br/>
                	
		      
                	
                	<table style="width: 95%; font-size:15px; margin-left:5%; padding-top:1px;">
		        		<tr>
		        		
		        			<td style="font-size:18px;width: 40%;text-align: right;"><span>		</span> Нягтлан бодогч: </td>
		        			<td style="text-align: center;width: 20%;"><img t-attf-src="data:image/jpg;base64,{{o.invoice_user_id.company_id.stamp}}" style="align:left; width:135px;height:105px;"/>			
		        			</td>
		        			<td style="margin-left:5%; font-size:12px;width: 40%;text-align: left;font-size:18px;"><span>		</span> /М.Пүрэвсүрэн/</td>
		        		</tr>
		        	</table> 
                </div>
                </t>
        

        </t>


        
