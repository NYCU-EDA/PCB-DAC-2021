# The PCB Benchmarks

## Introduction
NYCU CS EDA Lab’s PCB Router includes simultaneous escape routing (SER), post-SER refinement, and gridless area routing. To provide benchmarks for future research, we have released our PCB designs after removing any confidential information.

Input File of <case>:
1. <case>.benchmarking : The file used to record the net information of <case>.
Format: <net_id> p(<pin1_coor>) p(<pin2_coor>) <length_mathcing_group_id>  <spacing> <width> [feature]
2.	<case>.layer: The file used to note the avaiable layers of <case>.
Format: <Layer name> <Layer id>
#Only Top, Bottom, and Signal layers are able to be utilized for PCB routing.
3.	<case>.<Layer name>.obs: The file used to list the routing obstacles of <case>.
Format: ( x1 y1 x2 y2 x3 y3….)
4.	<case>.diff: The file used to list the differential pair of <case>.
Format: <net1 name> <net2 name> 
    
## Experiments
The solution result (.gds) can be checked using layout editors (e.g., klayout). The result includes the wires from SER and area routing, crossing-free edges, and fan-out candidates. The figure below shows the result of the b05 design (layer S5).
    

![](https://i.imgur.com/3LwdvvU.png)
The SER Result Obtained by NYCU CS EDA Lab’s PCB Router
    
    
| Benchmark | #Nets | #Available / Used Layers | #Utilized vias | #differential pair | 
| --------- | ---------------------------- | ------------------------ | -------------- |-------------- |
| b01       | 24                  | 2 / 2                    | 10             | 2 |
| b02       | 44                  | 3 / 3                    | 52             | 4 |
| b03       | 44                  | 3 / 3                    | 50             | 4 |
| b04       | 140                 | 4 / 4                    | 126            | 8 |
| b05       | 261                 | 7 / 6                    | 180            | 9 |
| b06       | 165                 | 7 / 6                    | 202            | 9 |
| b07       | 69                  | 5 / 5                    | 80             | 6 |
    
The results may differ slightly from those in [1] because the SAT solver can produce different results for the same problem.

To import the routing result into Cadence Allegro, a sub-drawing file (.clp) is required to represent the routing. However, this file may contain confidential information about the PCB design, so it is currently not allowed to be shared.
    
## Related Publications
[1] Shih-Ting Lin, Hung-Hsiao Wang, Chia-Yu Kuo, Yolo Chen, and Yih-Lang Li,“A Complete PCB Routing Methodology with Concurrent Hierarchical Routing,”IEEE/ACM Design Automation Conference (DAC), San Francisco, December 5–9, 2021.

If you use our PCB benchmarks or routing results in your publication, please cite paper [1].
    
## License Terms

READ THIS LICENSE AGREEMENT CAREFULLY BEFORE USING THIS PRODUCT. BY USING THIS PRODUCT YOU INDICATE YOUR ACCEPTANCE OF THE TERMS OF THE FOLLOWING AGREEMENT. THESE TERMS APPLY TO YOU AND ANY SUBSEQUENT LICENSEE OF THIS PRODUCT.

License Agreement
Copyright (c) 2021 by Shih-Ting Lin and Yih-Lang Li ("Authors") 
All right reserved 
Redistribution, with or without modification, are permitted provided that the following conditions are met:
1.	Redistributions must reproduce the above copyright notice, this list of conditions and the following disclaimer in the documentation and/or other materials provided with the distribution.
2.	Neither the names nor any trademark of the Authors may be used to endorse or promote products derived from this software without specific prior written permission.
3.	Use is limited to academic research groups only. Users who are interested in industry or commercial purposes must notify Authors and request separate license agreement.
    
THIS FREE SOFTWARE IS PROVIDED BY THE AUTHOR "AS IS" AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE DISCLAIMED. IN NO EVENT SHALL THE AUTHOR OR ANY CONTRIBUTOR BE LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT LIMITED TO, EFFECTS OF UNAUTHORIZED OR MALICIOUS NETWORK ACCESS; PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE, DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.
