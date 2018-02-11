
### Types

 - `/software/metaconfig/metaconfig_extension`
 - `/software/metaconfig/metaconfig_textrender_convert`
    - Description: 
    Convert value of certain types (e.g. boolean to string yes/no)
    (using the CCM::TextRender element options)

    - `/software/metaconfig/metaconfig_textrender_convert/yesno`
        - Description: Convert boolean to (lowercase) 'yes' and 'no'.
        - Optional
        - Type: boolean
    - `/software/metaconfig/metaconfig_textrender_convert/YESNO`
        - Description: Convert boolean to (uppercase) 'YES' and 'NO'.
        - Optional
        - Type: boolean
    - `/software/metaconfig/metaconfig_textrender_convert/truefalse`
        - Description: Convert boolean to (lowercase) 'true' and 'false'.
        - Optional
        - Type: boolean
    - `/software/metaconfig/metaconfig_textrender_convert/TRUEFALSE`
        - Description: Convert boolean to (uppercase) 'TRUE' and 'FALSE'.
        - Optional
        - Type: boolean
    - `/software/metaconfig/metaconfig_textrender_convert/doublequote`
        - Description: Convert string to doublequoted string.
        - Optional
        - Type: boolean
    - `/software/metaconfig/metaconfig_textrender_convert/singlequote`
        - Description: Convert string to singlequoted string.
        - Optional
        - Type: boolean
    - `/software/metaconfig/metaconfig_textrender_convert/joincomma`
        - Description: Convert list to comma-separated string
        - Optional
        - Type: boolean
    - `/software/metaconfig/metaconfig_textrender_convert/joinspace`
        - Description: Convert list to space-separated string
        - Optional
        - Type: boolean
    - `/software/metaconfig/metaconfig_textrender_convert/unescapekey`
        - Description: Unescape all dict keys
        - Optional
        - Type: boolean
    - `/software/metaconfig/metaconfig_textrender_convert/lowerkey`
        - Description: Convert all dict keys to lowercase
        - Optional
        - Type: boolean
    - `/software/metaconfig/metaconfig_textrender_convert/upperkey`
        - Description: Convert all dict keys to uppercase
        - Optional
        - Type: boolean
 - `/software/metaconfig/caf_service_action`
 - `/software/metaconfig/metaconfig_config`
    - `/software/metaconfig/metaconfig_config/mode`
        - Description: File permissions. Defaults to 0644.
        - Optional
        - Type: long
        - Default value: 420
    - `/software/metaconfig/metaconfig_config/owner`
        - Description: File owner. Defaults to root.
        - Optional
        - Type: string
        - Default value: root
    - `/software/metaconfig/metaconfig_config/group`
        - Description: File group. Defaults to root.
        - Optional
        - Type: string
        - Default value: root
    - `/software/metaconfig/metaconfig_config/daemons`
        - Description: An dict with foreach daemon the CAF::Service action to take
      if the file changes.
      Even if multiple services are associated to the same daemon, each action
      for the daemon will be taken at most once.
      If multiple actions are to be taken for the same daemon, all actions
      will be taken (no attempt to optimize is made).
        - Optional
        - Type: caf_service_action
    - `/software/metaconfig/metaconfig_config/module`
        - Description: Module to render the configuration file. See 'CONFIGURATION MODULES' in manpage.
        - Optional
        - Type: string
    - `/software/metaconfig/metaconfig_config/backup`
        - Description: Extension for the file's backup.
        - Optional
        - Type: string
    - `/software/metaconfig/metaconfig_config/preamble`
        - Description: Text to place at start of file.
      It can be useful to include context in a configuration file, in the form of
      a comment, such as how it was generated. Most of the formats that can be
      output by this component support "comment" lines, but none of the modules that
      it uses will generate them. The preamble attribute will be written out
      verbatim, before the contents is generated. No comment character is added,
      the user must specify this as part of the preamble string.
        - Optional
        - Type: string
    - `/software/metaconfig/metaconfig_config/contents`
        - Description: A free-form structure describing the valid entries for the
      configuration file. It is recommended to define another type for each
      config file, and bind it to these contents, to get the best validation.
        - Optional
        - Type: metaconfig_extension
    - `/software/metaconfig/metaconfig_config/convert`
        - Description: Predefined conversions from EDG::WP4::CCM::TextRender
        - Optional
        - Type: metaconfig_textrender_convert
 - `/software/metaconfig/metaconfig_component`
    - `/software/metaconfig/metaconfig_component/services`
        - Optional
        - Type: metaconfig_config
