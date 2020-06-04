# Ceramic Improvement Proposals (CIPs)

Ceramic Improvement Proposals (CIPs) describe standards for the Ceramic platform, including core protocol specifications, client APIs, and document standards.

## Contributing

> Below, find the end-to-end process of taking your CIP proposal from idea to finalization.

### 1. Propose a new IDEA as an issue

The first step in the CIP process is creating an IDEA proposal. To get started:

1. Create an issue in the CIP repository containing the idea for your your proposal following the [CIP template](https://github.com/ceramicnetwork/CIP/blob/master/.github/ISSUE_TEMPLATE/cip-template.md) format.
2. Give your issue a descriptive title, following the format: Category (or Type if n/a): Your Title
3. Add issue labels for `Type` and `Category` (See [below](#cip-labels) for descriptions)
4. Add the `Status: Idea` label 

> *Not all idea proposals need to be complete, however your issue should contain enough information for the community to begin commenting.*

### 2. Gather feedback from the community

After you submit your proposal as an idea, seek to engage the Ceramic community for feedback and input. You should take feedback into consideration and iterate on your idea if necessary.

### 2. Complete your issue as a draft

Once your idea has been considered by the community, you should complete the draft of your proposal by detailing out all sections of the issue template.

### 2. Submit your draft as a PR

Once your proposal draft has been completed, submit a Pull Request to this repository.

1. 

Your first PR should be a first draft of the final CIP. An editor will manually review the first PR for a new CIP and assign it a number before merging it. Make sure you include a discussions-to header with the URL to an open GitHub issue where people can discuss the CIP as a whole. (Ideally this is the original issue in the CIP repository.)

4. When the last call period is done and all community concerns have been addressed, fork the repository by clicking "Fork" in the top right.
5. Add your CIP to your fork of the repository.
6. Submit a Pull Request to Ceramic's CIPs repository.



2. Complete your proposal, then update your status to **DRAFT** Label and header.

### 3. Enter last call on your PR

3. Gather feedback from the community and iterate on your proposal. When done, update the status to **LAST CALL**.

### 4. Finalize your PR

The last step in

#### 4a. For CIP of Type Core

Get your core CIP accepted

#### 4b. For all other CIPs



> 

If your CIP requires images, the image files should be included in a subdirectory of the assets folder for that CIP as follows: `assets/cip-N` (where **N** is to be replaced with the CIP number). When linking to an image in the CIP, use relative links such as `../assets/cip-1/image.png`.

Make sure that the 'author' line of your CIP contains either your GitHub username or your email address. If you use your email address, that address must be the one publicly shown on your GitHub profile.

When you believe your CIP is mature and ready to progress past the draft phase, you should do one of two things:

- **For a Standards Track: Core CIP**, ask to have your issue added to the agenda of an upcoming Ceramic Core Devs meeting, where it can be discussed for inclusion in a future network upgrade. If implementers agree to include it, the CIP editors will update the state of your CIP to 'Accepted'.
- **For all other CIPs**, open a PR changing the state of your CIP to 'Final'. An editor will review your draft and ask if anyone objects to its being finalised. If the editor decides there is no rough consensus - for instance, because contributors point out significant issues with the CIP - they may close the PR and request that you fix the issues in the draft before trying again.

## CIP Labels

### CIP Types

- `Standards`:
- `Meta`:
- `Informational`:

### CIP Categories
> Only applicable to CIPs that are *Standards* type.

- `Core`:
- `Networking`:
- `Interface`:
- `RFC`:

### CIP Statuses

- `Idea`: an CIP that is incomplete.
- `Draft`: an CIP that is undergoing rapid iteration and changes.
- `Last Call`: an CIP that is done with its initial iteration and ready for review by a wide audience.
- `Accepted`: a core CIP that has been in Last Call for at least 2 weeks and any technical changes that were requested have been addressed by the author. The process for Core Devs to decide whether to encode an CIP into their clients as part of a network upgrade is not part of the CIP process. If such a decision is made, the CIP will move to final.
- `Final (non-Core)`: an CIP that has been in Last Call for at least 2 weeks and any technical changes that were requested have been addressed by the author.
- `Final (Core)`: an CIP that the Core Devs have decided to implement and release in a future network upgrade or has already been released.
