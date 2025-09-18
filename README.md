PSR-12 Extended Coding Standard
===============================

[![Latest Stable Version](http://poser.pugx.org/roslov/psr12ext/v)](https://packagist.org/packages/roslov/psr12ext)
[![Total Downloads](http://poser.pugx.org/roslov/psr12ext/downloads)](https://packagist.org/packages/roslov/psr12ext)
[![Latest Unstable Version](http://poser.pugx.org/roslov/psr12ext/v/unstable)](https://packagist.org/packages/roslov/psr12ext)
[![License](http://poser.pugx.org/roslov/psr12ext/license)](https://packagist.org/packages/roslov/psr12ext)
[![PHP Version Require](http://poser.pugx.org/roslov/psr12ext/require/php)](https://packagist.org/packages/roslov/psr12ext)

This repository extends the [PSR-12 coding style](https://www.php-fig.org/psr/psr-12/).

In addition to PSR-12 this coding style also contains some rules from
the [Slevomat Coding Standard](https://github.com/slevomat/coding-standard)
and [PHP_CodeSniffer](https://github.com/PHPCSStandards/PHP_CodeSniffer).


Using This Code Style
---------------------

After CodeSniffer is installed, you can launch it with a custom code style using the following syntax:

```sh
composer require --dev roslov/psr12ext
./vendor/bin/phpcs --extensions=php --standard=PSR12Ext /app
```

If you are planning to integrate the code quality check with your IDE or CI,
create the file `ruleset.xml` in the project’s root folder.

This file can include the list of rules you want to disable, as well as your custom settings. For example:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<ruleset name="project-code-styling">
    <description>Local Project Coding Standard</description>

    <!-- Excludes vendor and temporary folders -->
    <exclude-pattern>vendor/*</exclude-pattern>
    <exclude-pattern>var/*</exclude-pattern>

    <!-- Base standards (if not detected) -->
    <config name="installed_paths" value="vendor/roslov/psr12ext" />

    <!-- Base rules -->
    <rule ref="PSR12Ext">
        <!-- Ignores line endings -->
        <exclude name="Generic.Files.LineEndings" />
        <!-- Disables strict type requirement -->
        <exclude name="SlevomatCodingStandard.TypeHints.DeclareStrictTypes" />
        <!-- Ignores missing parentheses in class instantiation -->
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

All used rules with their options are described in [PSR12Ext/ruleset.xml](PSR12Ext/ruleset.xml).

Below you can find only names of the rules:

* **All rules of PSR12**:
    * _All rules of PSR1_:
        * Generic.Files.ByteOrderMark
        * Generic.NamingConventions.UpperCaseConstantName
        * Generic.PHP.DisallowAlternativePHPTags
        * Generic.PHP.DisallowShortOpenTag
        * Generic.PHP.DisallowShortOpenTag.EchoFound
        * Squiz.Classes.ValidClassName
    * Generic.ControlStructures.InlineControlStructure
    * Generic.Files.LineEndings
    * Generic.Files.LineLength
    * Generic.Formatting.DisallowMultipleStatements
    * Generic.Functions.FunctionCallArgumentSpacing
    * Generic.PHP.LowerCaseConstant
    * Generic.PHP.LowerCaseKeyword
    * Generic.PHP.LowerCaseType
    * Generic.WhiteSpace.DisallowTabIndent
    * Generic.WhiteSpace.IncrementDecrementSpacing
    * Generic.WhiteSpace.ScopeIndent
    * PEAR.Functions.ValidDefaultValue
    * PSR2.Classes.ClassDeclaration
    * PSR2.Classes.PropertyDeclaration
    * PSR2.ControlStructures.ElseIfDeclaration
    * PSR2.ControlStructures.SwitchDeclaration
    * PSR2.Files.ClosingTag
    * PSR2.Files.EndFileNewline
    * PSR2.Methods.FunctionCallSignature
    * PSR2.Methods.FunctionCallSignature.OpeningIndent
    * PSR2.Methods.FunctionCallSignature.SpaceAfterCloseBracket
    * PSR2.Methods.FunctionClosingBrace
    * PSR2.Methods.MethodDeclaration
    * PSR2.Methods.MethodDeclaration.Underscore
    * Squiz.ControlStructures.ControlSignature
    * Squiz.ControlStructures.ForEachLoopDeclaration
    * Squiz.ControlStructures.ForEachLoopDeclaration.AsNotLower
    * Squiz.ControlStructures.ForEachLoopDeclaration.SpaceAfterOpen
    * Squiz.ControlStructures.ForEachLoopDeclaration.SpaceBeforeClose
    * Squiz.ControlStructures.ForLoopDeclaration
    * Squiz.ControlStructures.ForLoopDeclaration.SpacingAfterOpen
    * Squiz.ControlStructures.ForLoopDeclaration.SpacingBeforeClose
    * Squiz.ControlStructures.LowercaseDeclaration
    * Squiz.Functions.FunctionDeclaration
    * Squiz.Functions.FunctionDeclarationArgumentSpacing
    * Squiz.Functions.LowercaseFunctionKeywords
    * Squiz.Functions.MultiLineFunctionDeclaration
    * Squiz.Scope.MethodScope
    * Squiz.WhiteSpace.CastSpacing
    * Squiz.WhiteSpace.ControlStructureSpacing.SpacingAfterOpen
    * Squiz.WhiteSpace.ControlStructureSpacing.SpacingBeforeClose
    * Squiz.WhiteSpace.ScopeClosingBrace
    * Squiz.WhiteSpace.ScopeKeywordSpacing
    * Squiz.WhiteSpace.SuperfluousWhitespace
    * Squiz.WhiteSpace.SuperfluousWhitespace.EmptyLines
    * Squiz.WhiteSpace.SuperfluousWhitespace.EndFile
    * Squiz.WhiteSpace.SuperfluousWhitespace.StartFile
* **Custom rules:**
    * Generic.Arrays.DisallowLongArraySyntax
    * Generic.CodeAnalysis.EmptyPHPStatement
    * Generic.CodeAnalysis.EmptyStatement
    * Generic.CodeAnalysis.JumbledIncrementer
    * Generic.CodeAnalysis.UnnecessaryFinalModifier
    * Generic.CodeAnalysis.UnusedFunctionParameter
    * Generic.CodeAnalysis.UselessOverridingMethod
    * Generic.ControlStructures.DisallowYodaConditions
    * Generic.Files.EndFileNewline
    * Generic.Files.ExecutableFile
    * Generic.Formatting.SpaceAfterCast
    * Generic.NamingConventions.InterfaceNameSuffix
    * Generic.NamingConventions.TraitNameSuffix
    * Generic.PHP.DisallowRequestSuperglobal
    * Generic.PHP.Syntax
    * Generic.Strings.UnnecessaryHeredoc
    * Generic.VersionControl.GitMergeConflict
    * Generic.WhiteSpace.HereNowdocIdentifierSpacing
    * Generic.WhiteSpace.SpreadOperatorSpacingAfter
    * PEAR.ControlStructures.ControlSignature
    * PSR1.Files.SideEffects
    * PSR1.Files.SideEffects.FoundWithSymbols
    * PSR12.Classes.AnonClassDeclaration
    * PSR12.Classes.ClosingBrace
    * PSR12.ControlStructures.BooleanOperatorPlacement
    * PSR12.ControlStructures.ControlStructureSpacing
    * PSR12.Files.DeclareStatement
    * PSR12.Files.FileHeader
    * PSR12.Files.ImportStatement
    * PSR12.Files.OpenTag
    * PSR12.Functions.ReturnTypeDeclaration
    * PSR12.Properties.ConstantVisibility
    * PSR12.Traits.UseDeclaration
    * PSR2.Methods.FunctionCallSignature.SpaceBeforeCloseBracket
    * SlevomatCodingStandard.Arrays.ArrayAccess
    * SlevomatCodingStandard.Arrays.DisallowImplicitArrayCreation
    * SlevomatCodingStandard.Arrays.DisallowPartiallyKeyed
    * SlevomatCodingStandard.Arrays.SingleLineArrayWhitespace
    * SlevomatCodingStandard.Arrays.TrailingArrayComma
    * SlevomatCodingStandard.Attributes.AttributeAndTargetSpacing
    * SlevomatCodingStandard.Attributes.AttributesOrder
    * SlevomatCodingStandard.Attributes.DisallowAttributesJoining
    * SlevomatCodingStandard.Attributes.DisallowMultipleAttributesPerLine
    * SlevomatCodingStandard.Attributes.RequireAttributeAfterDocComment
    * SlevomatCodingStandard.Classes.BackedEnumTypeSpacing
    * SlevomatCodingStandard.Classes.ClassConstantVisibility
    * SlevomatCodingStandard.Classes.ClassLength
    * SlevomatCodingStandard.Classes.ClassMemberSpacing
    * SlevomatCodingStandard.Classes.ClassStructure
    * SlevomatCodingStandard.Classes.ConstantSpacing
    * SlevomatCodingStandard.Classes.DisallowLateStaticBindingForConstants
    * SlevomatCodingStandard.Classes.DisallowMultiConstantDefinition
    * SlevomatCodingStandard.Classes.DisallowMultiPropertyDefinition
    * SlevomatCodingStandard.Classes.DisallowStringExpressionPropertyFetch
    * SlevomatCodingStandard.Classes.EnumCaseSpacing
    * SlevomatCodingStandard.Classes.MethodSpacing
    * SlevomatCodingStandard.Classes.ModernClassNameReference
    * SlevomatCodingStandard.Classes.ParentCallSpacing
    * SlevomatCodingStandard.Classes.PropertyDeclaration
    * SlevomatCodingStandard.Classes.PropertySpacing
    * SlevomatCodingStandard.Classes.RequireAbstractOrFinal
    * SlevomatCodingStandard.Classes.RequireMultiLineMethodSignature
    * SlevomatCodingStandard.Classes.RequireSelfReference
    * SlevomatCodingStandard.Classes.TraitUseSpacing
    * SlevomatCodingStandard.Classes.UselessLateStaticBinding
    * SlevomatCodingStandard.Commenting.AnnotationName
    * SlevomatCodingStandard.Commenting.DeprecatedAnnotationDeclaration
    * SlevomatCodingStandard.Commenting.DisallowCommentAfterCode
    * SlevomatCodingStandard.Commenting.DocCommentSpacing
    * SlevomatCodingStandard.Commenting.EmptyComment
    * SlevomatCodingStandard.Commenting.InlineDocCommentDeclaration
    * SlevomatCodingStandard.Commenting.UselessFunctionDocComment
    * SlevomatCodingStandard.Complexity.Cognitive
    * SlevomatCodingStandard.ControlStructures.DisallowContinueWithoutIntegerOperandInSwitch
    * SlevomatCodingStandard.ControlStructures.JumpStatementsSpacing
    * SlevomatCodingStandard.ControlStructures.LanguageConstructWithParentheses
    * SlevomatCodingStandard.ControlStructures.NewWithParentheses
    * SlevomatCodingStandard.ControlStructures.RequireNullCoalesceEqualOperator
    * SlevomatCodingStandard.ControlStructures.RequireNullCoalesceOperator
    * SlevomatCodingStandard.ControlStructures.RequireNullSafeObjectOperator
    * SlevomatCodingStandard.ControlStructures.UselessIfConditionWithReturn
    * SlevomatCodingStandard.ControlStructures.UselessTernaryOperator
    * SlevomatCodingStandard.Exceptions.DeadCatch
    * SlevomatCodingStandard.Exceptions.ReferenceThrowableOnly
    * SlevomatCodingStandard.Exceptions.RequireNonCapturingCatch
    * SlevomatCodingStandard.Files.FileLength
    * SlevomatCodingStandard.Functions.ArrowFunctionDeclaration
    * SlevomatCodingStandard.Functions.DisallowEmptyFunction
    * SlevomatCodingStandard.Functions.NamedArgumentSpacing
    * SlevomatCodingStandard.Functions.RequireTrailingCommaInCall
    * SlevomatCodingStandard.Functions.RequireTrailingCommaInClosureUse
    * SlevomatCodingStandard.Functions.RequireTrailingCommaInDeclaration
    * SlevomatCodingStandard.Functions.StaticClosure
    * SlevomatCodingStandard.Functions.UnusedInheritedVariablePassedToClosure
    * SlevomatCodingStandard.Functions.UselessParameterDefaultValue
    * SlevomatCodingStandard.Namespaces.AlphabeticallySortedUses
    * SlevomatCodingStandard.Namespaces.DisallowGroupUse
    * SlevomatCodingStandard.Namespaces.MultipleUsesPerLine
    * SlevomatCodingStandard.Namespaces.NamespaceDeclaration
    * SlevomatCodingStandard.Namespaces.NamespaceSpacing
    * SlevomatCodingStandard.Namespaces.ReferenceUsedNamesOnly
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
    * SlevomatCodingStandard.PHP.RequireExplicitAssertion
    * SlevomatCodingStandard.PHP.ShortList
    * SlevomatCodingStandard.PHP.UselessParentheses
    * SlevomatCodingStandard.PHP.UselessSemicolon
    * SlevomatCodingStandard.Strings.DisallowVariableParsing
    * SlevomatCodingStandard.TypeHints.DeclareStrictTypes
    * SlevomatCodingStandard.TypeHints.LongTypeHints
    * SlevomatCodingStandard.TypeHints.NullableTypeForNullDefaultValue
    * SlevomatCodingStandard.TypeHints.NullTypeHintOnLastPosition
    * SlevomatCodingStandard.TypeHints.ParameterTypeHint
    * SlevomatCodingStandard.TypeHints.ParameterTypeHintSpacing
    * SlevomatCodingStandard.TypeHints.PropertyTypeHint
    * SlevomatCodingStandard.TypeHints.ReturnTypeHint
    * SlevomatCodingStandard.TypeHints.ReturnTypeHintSpacing
    * SlevomatCodingStandard.TypeHints.UnionTypeHintFormat
    * SlevomatCodingStandard.TypeHints.UselessConstantTypeHint
    * SlevomatCodingStandard.Variables.DisallowSuperGlobalVariable
    * SlevomatCodingStandard.Variables.DuplicateAssignmentToVariable
    * SlevomatCodingStandard.Variables.UnusedVariable
    * SlevomatCodingStandard.Variables.UselessVariable
    * SlevomatCodingStandard.Whitespaces.DuplicateSpaces
    * Squiz.Classes.ClassDeclaration
    * Squiz.Classes.LowercaseClassKeywords
    * Squiz.Commenting.DocCommentAlignment
    * Squiz.Commenting.PostStatementComment
    * Squiz.PHP.NonExecutableCode
    * Squiz.Scope.StaticThisUsage
    * Squiz.Strings.ConcatenationSpacing
    * Squiz.Strings.DoubleQuoteUsage.NotRequired
    * Squiz.WhiteSpace.ControlStructureSpacing
    * Squiz.WhiteSpace.OperatorSpacing


Versioning
----------

PSR-12 Extended Coding Standard uses a `MAJOR.MINOR.PATCH` version number format.

The `MAJOR` version is incremented when:
- the major version of Slevomat Coding Standard is changed, or
- the major version of PHP_CodeSniffer is changed, or
- the major version of PHP is added, or
- the minor version of PHP is removed, or
- backward-incompatible changes are made to the `ruleset.xml` format, or
- existing sniffs are removed from this standard (removed from the list).

The `MINOR` version is incremented when:
- the minor version of Slevomat Coding Standard is changed, or
- the minor version of PHP_CodeSniffer is changed, or
- the minor version of PHP is added, or
- new sniffs are enabled in this standard (added to the list), or
- backward-compatible changes are made to the `ruleset.xml` format.

The `PATCH` version is incremented when:
- backward-compatible bug fixes are made.
