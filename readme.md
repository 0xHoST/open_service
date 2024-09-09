# OpenService - Ideation phase

An open protocol leveraging smart contracts for transparent service offerings within the sharing economy on public blockchains (e.g., TON Network, Arbitrum, Base). This project is purely for personal interest, aimed at helping me develop and learn smart contract programming using Solidity and Tact languages.

## Actors

1. Service Offerer (e.g., Driver, Airbnb Host)
2. Service Provider (e.g., Grab, Airbnb, )
3. Service User
4. Country-Specific Governance

## Explorer

1. Displays transactions for each completed service.
2. Displays the summary for each services offered by service providers.

## Modules

1. Service Module

            - Enables service offerers to register their services through the Service Provider Module by minting a soulbound token provided by the module.
            - During this process, the protocol verifies the service offerer against the Policy Registry Module before minting the soulbound token.
            - If the policy validation fails, the service registration will be rejected.

            - Allows users to book or make appointments (e.g., calling a driver) by minting a fractional, transferable service token (NFT) derived from the service offerer's soulbound token.
            - Users are required to pay to mint the service token, and the payment will be held in escrow until the service is successfully completed.

            - Facilitates service offerers, users, and service providers to mark a service as complete.
            - Upon completion, the contract marks the user's fractional service token as pending payment until the completion is confirmed.
            - The token is then transferred to the Track Module for record-keeping.

2. Registry Module

            - Each country will have its own policy contract that defines service validation methods. These contracts must be registered within the Policy Registry Module.
            - Allows country-specific governance to register their policy contract for validation checks.
            - Call governance policy contract checking method.
            - Calls the country’s policy contract to execute policy checks.
                - Assume service offerer already register their wallet information

3. Fee Distribution Module

            - Each service provider will have a specific fee distribution contract tied to the service type they offer.
            - The Service Module will call this Fee Distribution Module to distribute fees among the relevant actors once the service is marked complete.

4. Service Provider Module

            - Service providers register their service provider contracts within this module.
            - Each service provider can link multiple fee distribution contracts to their service provider contract.
            - These contracts are called when invoked by the Service Module to manage payments.

5. Dispute Resolver Module

            - When a user raises a dispute, the protocol identifies the relevant service and fetches the appropriate Dispute Resolver Module from the Service Provider Module.
            - The protocol creates a dispute contract, adds dispute resolver addresses, and resolver would need processes the dispute anad mark as resolved.
            - Once resolved, the protocol calls the Service Module to complete the service.

6. Track Module

            - Provides open data for governance, service providers, or users to track how many services have been completed by a specific wallet.

## Looking For Opportunities

I am actively seeking new job opportunities where I can contribute my skills and continue growing as a developer. If you're have a position that fits my profile, feel free to reach out! :(

Email: <hosiangtoon@gmail.com>
