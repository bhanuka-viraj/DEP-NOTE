
|                                                   |     |
| ------------------------------------------------- | --- |
| What is the data flow in <br>two way data binding |     |

### With HTML Elements

first import `FormsModule` in to the appComponent.ts
![[Pasted image 20240725190219.png]]

app compponent => 

Html => 

![[Pasted image 20240725190423.png]]

ts =>
![[Pasted image 20240725190604.png]]

### With Angular component

![[Pasted image 20240725193805.png]]

when parent range is changed the child rand should be changed accordingly. 

#### child component => 

html => 
![[Pasted image 20240725193455.png]]


ts => 
![[Pasted image 20240725193512.png]]


#### parent component => 

html => 

![[Pasted image 20240725193558.png]]

ts => 
![[Pasted image 20240725193645.png]]


Now create this when child is changed parent is changed

![[Pasted image 20240725194246.png]]

#### Child component => 

 html => 
 ![[Pasted image 20240726011621.png]]

ts =>
![[Pasted image 20240726011759.png]]


#### Parent Component => 

html => 

![[Pasted image 20240726011918.png]]


ts => 
![[Pasted image 20240726011952.png]]
Using two way data binding => 

to use two way data biding with angular component there is type convention. 

`input abc`
`input abcChanged`

