renderSBS alpha version 0.2
by Simone "Simplo" Murtas
https://github.com/simplo

It works, but has to be tested in different environments.
Probably it has still many problems to be fixed.
So why I released it?
Just because I don't really know when I fill find the time to test it properly, so maybe that if I wait it will never be released.

renderSBS is a TOX made to help testing SBS 3D projections.

I needed some kind of 3D content from TouchDesigner to test a 3D projector setup with acrive glasses.
Instead of waste time building different 3D scenarios, I tought it could be great to have a component able to be copied in any 3D TouchDesigner scenario (SOPs & Geos + camera + lights + render) and transform it in an SBS 3D output.

How to use it:
Just put renderSBS in the container with your main render: you just have to assign your existing render to the "render" parameter of the tox and get an SBS rendering as output, according to the "intereye" parameter you choose.
Parameters:
	- render -> the render object to process
	- type -> what kind of 3D mode you want
		TopBottom
		SideBySide
	- interEye -> distance between the two cameras. Increasing it will improve 3D effect, but too much will distorce image.	
	- POVmode -> how to set the POV (theorically the tz=0 means that SOPs beyond that value appears as "inside" the projection surface, the ones before that value appersa as "outside")
		at zero -> fixed at tz=0
		follow -> same as original (if present in the render, otherwise is set to 0), even if it's moving
		relative to camera -> always at a specific distance from camera
	- POVplane
		distance from camera for "relative to camera" mode




What it does:
Basically it takes the original point of view of the camera in your original render as LEFT EYE camera, then creates a RIGHT EYE camera at "intereye" distance from that and take both tangent to the point of view.
Theoretically you don't need to make anything, just set the "intereye" value as you like.
All rendering specs, camera movements etc will be replicated.

1) gets all the "render" parameter and duplicates them on the LEFT and RIGHT renders, so you'll get same results in term of lens, angle of view and flags.
2) use same lights as the original render
3) use same geos as the originale render
4) gets the original camera and set all the parameters to the two cameras (LEFT and RIGHT)
5) changes all the parameters in real time, so if your camera moves, for instance, also the two cameras will move in the same way.

Controls:
	- CTRL+3 / CTRL+4 decrease/increase the intereye value to set the best 3D effect. Steps are very small so you have to press them many times to see sibstantial diffrences.
	- CTRL+f shows the rendering in perform mode
	

Possible issues:
I'm sure renderSBS cannot work in every situation, the more your render is complicated the more are the probabilities of problems.
Probably I didn't considered any situation, especially in terms of elaborated camera movements (for example the path option etc).

Every feedback will be appreciated.

This program is free software: you can redistribute it and/or modify it under the terms of the GNU General Public License as published by the Free Software Foundation, either version 3 of the License, or (at your option) any later version.
Please mention the author.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with this program.  If not, see <http://www.gnu.org/licenses/>.


