# Quick-codes
First scripts

var encr = new GlideEncrypter(); 
var clearString = 'HtaL65969+MaqM43229+'; 
var encrString = encr.encrypt(clearString); 
gs.print("Encrypted string = " + encrString); 


var encr = new GlideEncrypter(); 
var encrString = 'KfQ2agULQTMbyGcVjzJ5Gdx/LpAT6p7l';
var decrString = encr.decrypt(encrString);  
gs.print("Decrypted string = " + decrString);
