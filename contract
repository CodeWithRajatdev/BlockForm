// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

contract BlockSubmit {
    struct JobEntry {
        uint256 id;
        address submitter;
        string title;
        string description;
        uint256 timestamp;
    }

    // Store all job entries
    JobEntry[] public jobEntries;

    // Event for new submissions
    event JobSubmitted(uint256 id, address indexed submitter, string title, uint256 timestamp);

    // Add a new job entry
    function submitJob(string memory _title, string memory _description) public {
        uint256 newId = jobEntries.length + 1;
        jobEntries.push(JobEntry(newId, msg.sender, _title, _description, block.timestamp));
        emit JobSubmitted(newId, msg.sender, _title, block.timestamp);
    }

    // Get total number of job entries
    function getTotalJobs() public view returns (uint256) {
        return jobEntries.length;
    }

    // Retrieve a specific job entry
    function getJob(uint256 _id) public view returns (JobEntry memory) {
        require(_id > 0 && _id <= jobEntries.length, "Invalid job ID");
        return jobEntries[_id - 1];
    }
}
