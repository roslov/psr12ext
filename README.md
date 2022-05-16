PSR-12 Extended Coding Standard
===============================

This repository extends the [PSR-12 coding style](https://www.php-fig.org/psr/psr-12/).

In addition to PSR-12 this coding style contains also some rules from
the [Slevomat Coding Standard](https://github.com/slevomat/coding-standard).


Using This Code Style
---------------------

After CodeSniffer is installed you can launch it with custom code style using the following syntax:

```sh
composer require --dev roslov/psr12ext
./vendor/bin/phpcs --extensions=php --standard=PSR12Ext /app
```

If you are planning to integrate the code quality check with you IDE or CI,
create the file `ruleset.xml` in the project’s root folder.

This file can include the list of rule you want to disable as well as your custom settings. For example:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<ruleset name="project-code-styling">
    <description>Local Project Coding Standard</description>

    <!-- Excludes vendor and temporary folders -->
    <exclude-pattern>vendor/*</exclude-pattern>
    <exclude-pattern>var/*</exclude-pattern>
    <exclude-pattern>tests/_support/*</exclude-pattern>

    <!-- Base standards -->
    <config name="installed_paths" value="vendor/roslov/psr12ext" />

    <!-- Base rules -->
    <rule ref="PSR12Ext">
        <!-- Ignores line endings -->
        <exclude name="Generic.Files.LineEndings" />
        <!-- Disables strict type requirement -->
        <exclude name="SlevomatCodingStandard.TypeHints.DeclareStrictTypes" />
        <!-- Ignores missing parentheses in class instantination -->
        <exclude name="PSR12.Classes.ClassInstantiation.MissingParentheses" />
    </rule>

    <!-- Rules for tests -->
    <rule ref="PSR1.Classes.ClassDeclaration.MissingNamespace">
        <exclude-pattern>tests/*</exclude-pattern>
    </rule>
    <rule ref="PSR2.Methods.MethodDeclaration.Underscore">
        <exclude-pattern>tests/*</exclude-pattern>
    </rule>
</ruleset>
```


The List Of Rules Used In This Coding Standard
----------------------------------------------

All used rules with their options are describled in [PSR12Ext/ruleset.xml](PSR12Ext/ruleset.xml).

Below you can find only the name of the rules:

* All rules of PSR12
* Generic.Arrays.DisallowLongArraySyntax
* Generic.Formatting.SpaceAfterCast
* SlevomatCodingStandard.Arrays.DisallowImplicitArrayCreation
* SlevomatCodingStandard.Arrays.SingleLineArrayWhitespace
* SlevomatCodingStandard.Arrays.TrailingArrayComma
* SlevomatCodingStandard.Classes.ClassConstantVisibility
* SlevomatCodingStandard.Classes.ClassMemberSpacing
* SlevomatCodingStandard.Classes.ClassStructure
* SlevomatCodingStandard.Classes.ConstantSpacing
* SlevomatCodingStandard.Classes.DisallowLateStaticBindingForConstants
* SlevomatCodingStandard.Classes.DisallowMultiConstantDefinition
* SlevomatCodingStandard.Classes.DisallowMultiPropertyDefinition
* SlevomatCodingStandard.Classes.MethodSpacing
* SlevomatCodingStandard.Classes.ModernClassNameReference
* SlevomatCodingStandard.Classes.PropertySpacing
* SlevomatCodingStandard.Classes.RequireAbstractOrFinal
* SlevomatCodingStandard.Classes.TraitUseSpacing
* SlevomatCodingStandard.Classes.UselessLateStaticBinding
* SlevomatCodingStandard.Commenting.DeprecatedAnnotationDeclaration
* SlevomatCodingStandard.Commenting.DisallowCommentAfterCode
* SlevomatCodingStandard.Commenting.DocCommentSpacing
* SlevomatCodingStandard.Commenting.EmptyComment
* SlevomatCodingStandard.Commenting.InlineDocCommentDeclaration
* SlevomatCodingStandard.Commenting.UselessFunctionDocComment
* SlevomatCodingStandard.ControlStructures.DisallowContinueWithoutIntegerOperandInSwitch
* SlevomatCodingStandard.ControlStructures.LanguageConstructWithParentheses
* SlevomatCodingStandard.ControlStructures.RequireNullCoalesceEqualOperator
* SlevomatCodingStandard.ControlStructures.RequireNullCoalesceOperator
* SlevomatCodingStandard.ControlStructures.UselessIfConditionWithReturn
* SlevomatCodingStandard.ControlStructures.UselessTernaryOperator
* SlevomatCodingStandard.Exceptions.DeadCatch
* SlevomatCodingStandard.Exceptions.ReferenceThrowableOnly
* SlevomatCodingStandard.Exceptions.RequireNonCapturingCatch
* SlevomatCodingStandard.Functions.ArrowFunctionDeclaration
* SlevomatCodingStandard.Functions.DisallowEmptyFunction
* SlevomatCodingStandard.Functions.StaticClosure
* SlevomatCodingStandard.Functions.UnusedInheritedVariablePassedToClosure
* SlevomatCodingStandard.Functions.UselessParameterDefaultValue
* SlevomatCodingStandard.Namespaces.AlphabeticallySortedUses
* SlevomatCodingStandard.Namespaces.DisallowGroupUse
* SlevomatCodingStandard.Namespaces.MultipleUsesPerLine
* SlevomatCodingStandard.Namespaces.NamespaceDeclaration
* SlevomatCodingStandard.Namespaces.NamespaceSpacing
* SlevomatCodingStandard.Namespaces.RequireOneNamespaceInFile
* SlevomatCodingStandard.Namespaces.UnusedUses
* SlevomatCodingStandard.Namespaces.UseDoesNotStartWithBackslash
* SlevomatCodingStandard.Namespaces.UselessAlias
* SlevomatCodingStandard.Namespaces.UseSpacing
* SlevomatCodingStandard.Operators.NegationOperatorSpacing
* SlevomatCodingStandard.Operators.RequireCombinedAssignmentOperator
* SlevomatCodingStandard.Operators.SpreadOperatorSpacing
* SlevomatCodingStandard.PHP.ForbiddenClasses
* SlevomatCodingStandard.PHP.OptimizedFunctionsWithoutUnpacking
* SlevomatCodingStandard.PHP.ShortList
* SlevomatCodingStandard.PHP.UselessParentheses
* SlevomatCodingStandard.PHP.UselessSemicolon
* SlevomatCodingStandard.TypeHints.DeclareStrictTypes
* SlevomatCodingStandard.TypeHints.LongTypeHints
* SlevomatCodingStandard.TypeHints.NullableTypeForNullDefaultValue
* SlevomatCodingStandard.TypeHints.NullTypeHintOnLastPosition
* SlevomatCodingStandard.TypeHints.ParameterTypeHint
* SlevomatCodingStandard.TypeHints.ParameterTypeHintSpacing
* SlevomatCodingStandard.TypeHints.PropertyTypeHint
* SlevomatCodingStandard.TypeHints.PropertyTypeHintSpacing
* SlevomatCodingStandard.TypeHints.ReturnTypeHint
* SlevomatCodingStandard.TypeHints.ReturnTypeHintSpacing
* SlevomatCodingStandard.TypeHints.UnionTypeHintFormat
* SlevomatCodingStandard.TypeHints.UselessConstantTypeHint
* SlevomatCodingStandard.Variables.DisallowSuperGlobalVariable
* SlevomatCodingStandard.Variables.DuplicateAssignmentToVariable
* SlevomatCodingStandard.Variables.UnusedVariable
* SlevomatCodingStandard.Variables.UselessVariable
* Squiz.ControlStructures.ControlSignature
* Squiz.Strings.ConcatenationSpacing
* Squiz.Strings.DoubleQuoteUsage.NotRequired
* Squiz.WhiteSpace.SuperfluousWhitespace


Versioning
----------

PSR-12 Extended Coding Standard uses a `MAJOR.MINOR.PATCH` version number format.

The `MAJOR` version is incremented when:
- the major version of Slevomat Coding Standard is changed, or
- the major version of PHP_CodeSniffer is changed, or
- backwards-incompatible changes are made to the `ruleset.xml` format, or
- new sniffs are enabled in this standard (added to the list), or
- existing sniffs are removed from this standard (removed from the list).

The `MINOR` version is incremented when:
- the minor version of Slevomat Coding Standard is changed, or
- the minor version of PHP_CodeSniffer is changed, or
- backwards-compatible changes are made to the `ruleset.xml` format.

The `PATCH` version is incremented when:
- backwards-compatible bug fixes are made.
