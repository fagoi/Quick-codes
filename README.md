# Quick-codes
First scripts

Glide Encrypter
var encr = new GlideEncrypter(); 
var clearString = 'HtaL65969+MaqM43229+'; 
var encrString = encr.encrypt(clearString); 
gs.print("Encrypted string = " + encrString); 


var encr = new GlideEncrypter(); 
var encrString = 'KfQ2agULQTMbyGcVjzJ5Gdx/LpAT6p7l';
var decrString = encr.decrypt(encrString);  
gs.print("Decrypted string = " + decrString);


Changing Scope

var db = new GlideDBQuery("sc_cat_item_producer");
db.addQuery("sys_id", "77aeb9d0dba08740a35dba9ffe9619a0");
var upd = new GlideDBUpdate("sc_cat_item_producer");
upd.setQuery(db);
upd.setValue("sys_scope" , "d4ac3fff5b311200a4656ede91f91af2");
upd.execute();


Force Record into update set

var current=new GlideRecord('Table');
current.addQuery('sys_id','');
current.query();
if(current.next()){
   var um = new GlideUpdateManager2();
   um.saveRecord(current);
}


GlideRecord (with callback)

 var gr = new GlideRecord('incident');
 gr.addQuery('number', g_form.getValue('related_incident'));
 gr.query(function(gr) {
     gr.next();
     g_form.setValue('u_related_incident_description', gr.short_description);

 });
 
 
 Clean email outbox
 deleteRec();
function deleteRec()
{
var gr = new GlideRecord("sys_email");
  gr.addQuery('mailbox', 'outbox');
  gr.query();
while (gr.next()) {
gr.setWorkflow(false);
gr.deleteMultiple();
  }
}

