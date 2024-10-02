Right now, it is October 2nd, 12:08 a.m.

For the past two hours, I have taught myself with the help of chatgpt-4o how to compile c-files from a tar-gz file, the significance of compiling, and the significance of the /usr and /usr/bin directories within the file system. All this experience came from deal.ii failing to run from an `apt` install, requiring me to build deal.ii from its source code.

At this moment, I debate whether it is better to have the new students use ElmerFEM or deal.ii.
On one hand, ElmerFEM is much easier to use, but just like me, in the real world, they will inevitably run into a problem which is not solvable by ElmerFEM and will require custom programming. Eventually, down the simulation road, they must learn how to use Linux, compile files, and code using C++, just as I have had to in the past few months as I advance toward my ambitions.
\
I therefore believe it is a service to teach these students how to dual boot and compile files, given that these are essential skills for any simulator, moreover justified by the fact that this initial effort will be negligible compared to the time they will spend trying to troubleshoot simulations. 

Documentation wise, deal.ii is still incontestable by either FEniCSx or ElmerFEM. It's tutorials are the best, and although FEniCSx is written in Python (which is somewhat easier than C++), learning the language of computers will still be less work than learning the language of simulations. The difference between Python and C++ is only syntax while the main challenge ahead is learning PDE solutions in both cases.

I therefore think we should move forward with the permanent implementation of the most powerful, most useful, and most reliably documented FEM tool which is deal.ii.

If necessary, I can derive and write a modesolver in deal.ii. This will be the easiest way to write a modesolver in my opinion, versus writing it in FEniCSx and ElmerFEM, due to documentation reasons. In this way, students will learn undeniably important ways of using computers which will prepare them for the real issues they will encounter in their professional lives, while also being able to use simulations without needing to derive them. This, I think, is the best of both worlds and will make this program well worth their time and money.

I am willing to write concise tutorials explaining precisely what they need to know about virtual file systems, terminal commands, and computer languages to allow them to perform simulations and deal with setbacks.

- Frank Dininno, October 2nd, 12:35 a.m.