# Asych-API-request
 
request.onload = function() {
 if (this.status >= 200 && this.status < 300) {
 if(request.response) {
 // Assuming a successful call returns JSON
 resolve(JSON.parse(request.response));
 } else {
 resolve();
 } else {
 reject({
 'status': this.status,
 'message': request.statusText
 });
 }
};
request.onerror = function() {
 reject({
 'status': this.status,
 'message': request.statusText
 });
};
