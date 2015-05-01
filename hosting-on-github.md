# Hosting http://srfi.schemers.org/ on Github

I propose that we move the hosting of SRFIs to Github.  This will eliminate hosting costs and low-level system administration work, and will make it easier for editors and others to contribute because Git, Subversion, and all of Github's tools will be available for use.

I've created this repository by running <cvs2git> on the existing <srfi.schemers.org> CVS repository, module "srfi", which I fetched on Thu 30 Apr 2015.  Until the official switch to Github, I'll keep it up to date as new changes are made in CVS.  All the existing content is in the <gh-pages> branch so that Github will host it directly.  The mailing list archives are not included in the CVS repository, but they will be preserved.

I have found a mailing list hosting provider, [simplelists.com](https://www.simplelists.com), who can host all of our mailing lists.  They will messages, archive them on the web, and handle subscription and unsubscription. They've agreed to upload our existing mailing list archives into the web archives they host and to make it possible for us to download new messages periodically.

I'm making a few changes to the repository after conversion from CVS:

- Add "README.md" and this document, "hosting-on-github.md", both in the <master> branch.  (The "README.md" file is what users first see when visiting the home page for this repository on Github.)

- Temporarily add a "CNAME" file pointing to "srfi.speechcode.com", a domain I control, so that I can test Github's domain hosting. Eventually, when we change the DNS address <srfi.schemers.org> to point to Github, I'll switch "CNAME" to "srfi.schemers.org" so that most existing links will continue to work.

- Update every reference to the old way of subscribing and unsubscribing to mailing lists to use the Simplelists web forms. (Since there are so many such pages, I've included a trivial template engine and other code for automating that update.)

- Update and revise some of the text on the administrative pages.

- Replace links using all "viewcvs" URLs of previous revisions of SRFIs with ones pointing at versions explicitly checked into Git.

- Extract the contents of all ".tar.gz" files so that individual implementation files are accessible directly

- Check in all existing mailing list archives.

- Point currently active (and future) archives to Simplelists, where they'll be uploaded.

- Temporarily change all links to <srfi.schemers.org> to equivalent links on <srfi.speechcode.com> so that I can test before the DNS change.  I'll undo that change when we move the DNS for <srfi.schemers.org> to point to Github.

I believe that this will be a good way to continue the SRFI process, minimize the editors' workload, and make contributions easier.

Michael Sperber [has approved](http://permalink.gmane.org/gmane.lisp.scheme.srfi.announce/117) this proposal, so I'm working on implementing it.

— Arthur A. Gleckler