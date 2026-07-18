# New-DLGroup
    ##SYNOPSIS
        Create a DL group

    ## DESCRIPTION
         The New-DLGroup creates a mail-enabled distribution group and automatically stores the group in DL Group OU.
            
        The function automatically:

        - Creates a Global Distribution Group.
        - Stores the group in the DL Groups OU.
        - Sets the sAMAccountName to match the group name.
        - Creates the primary email address by appending "@contoso.com" to the
            value supplied for the Email parameter.
        - Checks whether a group with the same sAMAccountName already exists before
            creating the group.       

    ## PARAMETER Name
        Specifies the display name, sAMAccountName, and Active Directory name of the
        distribution group.

        The name must be unique within Active Directory.

    ## PARAMETER Email
        Specifies only the email alias.

        Do not include the domain name. For example, enter:

            Sales

        instead of:

            sales@contoso.com

        The function automatically creates the email address using the
            contoso.com domain.

    ## EXAMPLE
        New-DLGroup -Name "Finance Team" -Email Finance

        Creates a distribution group named "Finance Team" and assigns the email
        address:

        Finance@contoso.com

    ## EXAMPLE
        New-DLGroup

        Prompts for the Name and Email parameters interactively.

    ## INPUTS
        System.String

    ## OUTPUTS
        Microsoft.ActiveDirectory.Management.ADGroup

    ## NOTE
        Version: 1.0

        Requirements:
        - Active Directory PowerShell module
        - Appropriate permissions to create groups
        - The "DL Groups" OU must exist
    
    ## License

        This project is licensed under the MIT License. See the `LICENSE` file for details.
