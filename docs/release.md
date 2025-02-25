# How to release firmware using GitHub Actions

Firmware releases are performed through Github Actions.
The overall process is to first tag the repo and then build it on Github Actions. The build will run tests, build binaries, generate a release in GitHub and upload binaries.

Continue to read here for a full detailed checklist for handling of full fw releases and release candidates.

**Note: For releasing Python libraries we currently follow instructions in an internal document.**

## 1. Pre-releasing firmware repositories
1. Tag the to-be-released GitHub repositories with a release candidate tag in the form of `2022.03-rc1`.
2. In GitHub Actions in each repository:
   * Select the 'release' flow.
   * Press the down arrow on 'run workflow'.
   * Select the release candidate tag (see screenshot under).
   * Press the green button 'Run workflow'.
3. Wait until the workflow has been finalized.
4. Make the pre-releases of the repositories public.

![](images/action_screenshot.png)

## 2. Make a candidate release firmware zip folder
1. Locally clone this repository (`git clone git@github.com:bitcraze/crazyflie-release.git`)
2. Modify the `versions.json` file:
   * Ensure the `crazyflie-release-version` reflects the overall release version (e.g., `2022.03-rc1` for the first release candidate).
   * Update all relevant firmware versions to their respective release candidate tags.
3. Tag the crazyflie-release repository with the candidate release tag (e.g., `2022.03-rc1`). The tag **must be identical** to the `crazyflie-release-version` specified in `versions.json` to maintain versioning consistency.
4. Go to the actions tab, select release, start the workflow with the candidate release tag (like with the other repositories)
5. Wait until workflow has been finalized, go to the draft release. Use the zip folder to flash the release candidate.

## 3. Perform release testing
1. Perofrm all the release testing
    * If all is good, continue!
    * If there is something wrong, fix the issues, and start again to generate a new version (e.g. `2022.03-rc2`) of the release candidate for both the firmware and again of the full crazyflie-release

## 4. Releasing firmware repositories
1. Now getting ready for the real release: set the real release tag (like `2022.03`) on the to-be-released GitHub repositories.
2. Use the release actions with that tag
3. On Github go to Releases, click the latest draft release, select the current and previous release's tags and click "Generate release notes".
4. Add a section containing all deprecated functionality in the code base (search for "deprecated").
5. Publish the firmware releases ("Set as latest release" checkbox selected)

## 5 Publish the real release
1. Tag the `crazyflie-release` repository with the release version (e.g. `2022.03`)
2. Use the 'release' workflow to generate a draft release
3. Go to the draft release:
    * add some general, human readable notes about the release (based on the release notes for the firmwares)
    * check the "set as latest release" checkbox
    * publish
4. Flash the release .zip files to check if they are working 
5. Don't forget to write a blogpost about the release
