# FamilyTree
Genealogy or Family tree application using the clean architecture and justifying the use of the same.
               +-----------------------------------+
               |         Presentation Layer         |
               |------------------------------------|
               | Genealogy.Console (Program.cs)     |
               +------------------------------------+
                             ↓ depends on
               +-----------------------------------+
               |       Application Layer            |
               |------------------------------------|
               | UseCases: AddFamilyMember, GetTree |
               | Services: FamilyMemberService,     |
               |            IFamilyMemberService    |
               | Mapper: Mapper.cs                  |
               | Models: FamilyMemberDto, TreeDto   |
               | DI: AddApplicationServices          |
               +------------------------------------+
                             ↓ depends on
               +-----------------------------------+
               |            Domain Layer            |
               |------------------------------------|
               | Entities: FamilyMember,            |
               |            FamilyRelationship      |
               | Repositories: IFamilyMemberRepo    |
               | Services: FamilyTreeValidator      |
               +------------------------------------+
                             ↑ depends on
               +-----------------------------------+
               |          Infrastructure Layer      |
               |------------------------------------|
               | Persistence: InMemoryFamilyRepo    |
               | DI: DependencyInjection.cs         |
               +------------------------------------+

                             ↑
               +-----------------------------------+
               |           Test Layer              |
               |------------------------------------|
               | Genealogy.Tests                   |
               |  └── Application                  |
               |       └── AddFamilyMemberTests.cs |
               +-----------------------------------+
