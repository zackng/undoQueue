# undoQueue

<h3>JS 'undo queue'</h3>
<p>Methods to temporary store an array of objects / values and 'Undo it'.
This is a method that I am using for Fiesto.co . 
No dependency. Pure js.</p>

<h3>Instruction to use</h3>
<p>
Before starting, you need to create a new instance like <code>var undoImageQueue = new undoQueue();</code>
</p>

<h4>User Parameters</h4>
<p>stepLimit - set a number. if empty, defaults to 69. Once the number of Array elements reach this limit, the oldest element( the first) will be removed 
and make way for new element</p>
<code>var undoImageQueue = new undoQueue({
stepLimit : 39});</code>

<h4>Methods</h4>
<p>remove(obj) - obj can be an object, string or number.</p>
<code>undoImageQueue.remove({imageId : 12345, removedTime : Date.now()});</code>

<p>onAfterRemoved(err, res) - When remove() is called, this method will be called and returns the object/value as <i>res</i>.</p>
<code>undoImageQueue.onAfterRemoved = function(err, res){<br/>
// Do sth
if(err){
//do sth
}
else{
//use the res and do sth with it.
}

}</code>
<p>undo() - removed the last element from the queue array.</p>
<code>undoImageQueue.undo();</code>
