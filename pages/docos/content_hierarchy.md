---
title: Content hierarchy
permalink: content-hierarchy.html
folder: docos\
---


The hierarchy goes from levels 1 through 5.  The 4th page in the 2nd level-3-branch of the 5th level-2-branch of the 10th level 1 branch would have the following tags in its frontmatter:
    lvl1.idx: 10
    lvl2.idx: 5
    lvl3.idx: 2
    lvl4.idx: 4
    lvl5.name: "some page name"

There will be a "root" page for each branch of the hierarchy that not be published, but will host any "level"-scoped data.  If we're going to have four level1/root branches, we'll create four pages, with the following frontmatter:

--
lvl1.idx: 1
lvl1.name: "Amazon Afilliate Link"
gotourl: "https://www.amazon.com/menckend"
--

--
lvl1.idx: 2
lvl1.name: "Diary Entries"
--

--
lvl1.idx: 3
lvl1.name: "Grocery Lists"
--

--
lvl1.idx: 4
lvl1.name: "Shout Outs"
--

That should result in a top-nav bar with 4 buttons:
    "Amazon Affiliate Link"   (a/href link that opens the gotourl)
    "Diary Entries"           (a dropdown menu populated with all of the l2 branches under l1.idx:2; that populates the sidenav with l1.idx:2 plusl2.idx:0-n entries)
    "Grocery Lists"           (a dropdown menu populated with all of the l2 branches under l1.idx:3; that populates the sidenav with l1.idx:3 plus l2.idx:0-n entries)
    "Shout outs"              (a dropdown menu populated with all of the l2 branches under l1.idx:3; that populates the sidenav with l1.idx:4 plus l2.idx:0-n entries)


So, for diary-entries, we'd need pages:

--
lvl1.idx: 2
lvl2.idx: 1
lvl2.name: "2023"
--

--
lvl1.idx: 2
lvl2.idx: 2
lvl2.name: "2022"
--

^Those establish that there *are* "2023" and "2022" level-2 branches under lvl1.idx2 ("Diary Entries")
